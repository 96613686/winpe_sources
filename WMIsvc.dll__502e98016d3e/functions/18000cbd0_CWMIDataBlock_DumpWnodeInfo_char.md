# CWMIDataBlock::DumpWnodeInfo(char *)

- ea: `0x18000cbd0`
- end: `0x18000ce86`
- name: `?DumpWnodeInfo@CWMIDataBlock@@IEAAJPEAD@Z`
- size: `694`
- prototype: `__int64 __fastcall(CWMIDataBlock *__hidden this, char *)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180007ebc`
- `0x18000ac5c`
- `0x18000ca8c`
- `0x18001c704`

## callees

- `0x180003e10`
- `0x18000cbd0`
- `0x1800101e4`
- `0x18001c030`
- `0x18001c0f8`
- `0x18001c1a8`
- `0x18001d377`

## import_xrefs

- `wbemcomn!DebugTrace` at `0x18000cc4c`
- `wbemcomn!DebugTrace` at `0x18000cc66`
- `wbemcomn!DebugTrace` at `0x18000cc81`
- `wbemcomn!DebugTrace` at `0x18000cc9c`
- `wbemcomn!DebugTrace` at `0x18000ccbc`
- `wbemcomn!DebugTrace` at `0x18000ccd7`
- `wbemcomn!DebugTrace` at `0x18000ccf2`
- `wbemcomn!DebugTrace` at `0x18000cd27`
- `wbemcomn!DebugTrace` at `0x18000cd46`
- `wbemcomn!DebugTrace` at `0x18000cd6f`
- `wbemcomn!DebugTrace` at `0x18000cdce`
- `wbemcomn!DebugTrace` at `0x18000ce56`
- `wbemcomn!DebugTrace` at `0x18000cc4c`
- `wbemcomn!DebugTrace` at `0x18000cc66`
- `wbemcomn!DebugTrace` at `0x18000cc81`
- `wbemcomn!DebugTrace` at `0x18000cc9c`
- `wbemcomn!DebugTrace` at `0x18000ccbc`
- `wbemcomn!DebugTrace` at `0x18000ccd7`
- `wbemcomn!DebugTrace` at `0x18000ccf2`
- `wbemcomn!DebugTrace` at `0x18000cd27`
- `wbemcomn!DebugTrace` at `0x18000cd46`
- `wbemcomn!DebugTrace` at `0x18000cd6f`
- `wbemcomn!DebugTrace` at `0x18000cdce`
- `wbemcomn!DebugTrace` at `0x18000ce56`
- `wbemcomn!ErrorTrace` at `0x18000cc15`
- `wbemcomn!ErrorTrace` at `0x18000cc25`
- `wbemcomn!ErrorTrace` at `0x18000cc35`
- `wbemcomn!ErrorTrace` at `0x18000cc15`
- `wbemcomn!ErrorTrace` at `0x18000cc25`
- `wbemcomn!ErrorTrace` at `0x18000cc35`
- `wbemcomn!LoggingLevelEnabled` at `0x18000cbfd`
- `wbemcomn!LoggingLevelEnabled` at `0x18000cbfd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000ce6a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000ce6a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000cdaf`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000cdaf`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000cd13`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000cd13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cd54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cd54`

## string_xrefs

- `0x18000ccb2`: `  Linkage...........%x\n`
- `0x18000cdc4`: `Writing out buffer, total size to write: %ld\n`

## pseudocode

```c
__int64 __fastcall CWMIDataBlock::DumpWnodeInfo(const void **this, char *a2)
{
  int v3; // r8d
  const IID *v4; // rcx
  unsigned int *v5; // r15
  unsigned int v6; // r15d
  void *v7; // r14
  unsigned __int8 *v8; // rbp
  unsigned int i; // r12d
  LPOLESTR lpsz; // [rsp+B0h] [rbp+8h] BYREF

  if ( this[16] )
  {
    CWMIDataBlock::DumpWnodeMsg((CWMIDataBlock *)this, a2);
    if ( LoggingLevelEnabled(1u) )
    {
      ErrorTrace(10, "*******************************************\n");
      ErrorTrace(10, "Enable verbose logging for more information\n");
      ErrorTrace(10, "*******************************************\n");
    }
    DebugTrace(10, "WNODE_HEADER 0x%x\n", (unsigned int)this[16]);
    DebugTrace(10, "  BufferSize........0x%x\n", *(_DWORD *)this[16]);
    DebugTrace(10, "  ProviderId........0x%x\n", *((_DWORD *)this[16] + 1));
    DebugTrace(10, "  Version...........0x%x\n", *((_DWORD *)this[16] + 2));
    v3 = *((_DWORD *)this[16] + 3);
    if ( v3 )
      DebugTrace(10, "  Linkage...........%x\n", v3);
    DebugTrace(10, "  TimeStamp:LowPart.0x%x\n", *((_DWORD *)this[16] + 4));
    DebugTrace(10, "  TimeStamp:HiPart..0x%x\n", *((_DWORD *)this[16] + 5));
    v4 = (const IID *)((char *)this[16] + 24);
    lpsz = 0;
    if ( !StringFromCLSID(v4, &lpsz) )
    {
      DebugTrace(10, "  Guid..............");
      TranslateAndLog(lpsz, 1);
      DebugTrace(10, "\n");
      CoTaskMemFree(lpsz);
    }
    DebugTrace(10, "  Flags.............0x%x\n", *((_DWORD *)this[16] + 11));
    if ( this[14] )
      CWMIDataBlock::DumpSingleWnode((CWMIDataBlock *)this);
    if ( this[15] )
      CWMIDataBlock::DumpAllWnode((CWMIDataBlock *)this);
    v5 = (unsigned int *)this[16];
    if ( v5 )
    {
      v6 = *v5;
      v7 = CWin32DefaultArena::WbemMemAlloc(v6 + 256);
      if ( v7 )
      {
        DebugTrace(10, "Writing out buffer, total size to write: %ld\n", v6);
        memset_0(v7, 0, v6 + 256);
        memcpy_0(v7, this[16], v6);
        v8 = (unsigned __int8 *)v7;
        for ( i = 0; i < v6; i += 10 )
        {
          DebugTrace(
            10,
            "  %02x %02x %02x %02x %02x %02x %02x %02x %02x %02x  \n",
            *v8,
            v8[1],
            v8[2],
            v8[3],
            v8[4],
            v8[5],
            v8[6],
            v8[7],
            v8[8],
            v8[9]);
          v8 += 10;
        }
        CWin32DefaultArena::WbemMemFree(v7);
      }
    }
  }
  return 2147749917LL;
}

```

## disassembly

```asm
0x18000cbd0  push    rbx
0x18000cbd2  push    rbp
0x18000cbd3  push    rsi
0x18000cbd4  push    rdi
0x18000cbd5  push    r12
0x18000cbd7  push    r13
0x18000cbd9  push    r14
0x18000cbdb  push    r15
0x18000cbdd  sub     rsp, 68h
0x18000cbe1  xor     esi, esi
0x18000cbe3  mov     rbx, rcx
0x18000cbe6  cmp     [rcx+80h], rsi
0x18000cbed  jz      loc_18000CE70
0x18000cbf3  call    ?DumpWnodeMsg@CWMIDataBlock@@IEAAXPEAD@Z; CWMIDataBlock::DumpWnodeMsg(char *)
0x18000cbf8  lea     edi, [rsi+1]
0x18000cbfb  mov     ecx, edi
0x18000cbfd  call    cs:__imp_?LoggingLevelEnabled@@YAHK@Z; LoggingLevelEnabled(ulong)
0x18000cc03  lea     r13d, [rsi+0Ah]
0x18000cc07  test    eax, eax
0x18000cc09  jz      short loc_18000CC3B
0x18000cc0b  lea     rdx, asc_180026D78; "***************************************"...
0x18000cc12  mov     ecx, r13d
0x18000cc15  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x18000cc1b  lea     rdx, aEnableVerboseL; "Enable verbose logging for more informa"...
0x18000cc22  mov     ecx, r13d
0x18000cc25  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x18000cc2b  lea     rdx, asc_180026D78; "***************************************"...
0x18000cc32  mov     ecx, r13d
0x18000cc35  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x18000cc3b  mov     r8, [rbx+80h]
0x18000cc42  lea     rdx, aWnodeHeader0xX; "WNODE_HEADER 0x%x\n"
0x18000cc49  mov     ecx, r13d
0x18000cc4c  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000cc52  mov     r8, [rbx+80h]
0x18000cc59  lea     rdx, aBuffersize0xX; "  BufferSize........0x%x\n"
0x18000cc60  mov     ecx, r13d
0x18000cc63  mov     r8d, [r8]
0x18000cc66  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000cc6c  mov     r8, [rbx+80h]
0x18000cc73  lea     rdx, aProviderid0xX; "  ProviderId........0x%x\n"
0x18000cc7a  mov     ecx, r13d
0x18000cc7d  mov     r8d, [r8+4]
0x18000cc81  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000cc87  mov     r8, [rbx+80h]
0x18000cc8e  lea     rdx, aVersion0xX; "  Version...........0x%x\n"
0x18000cc95  mov     ecx, r13d
0x18000cc98  mov     r8d, [r8+8]
0x18000cc9c  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000cca2  mov     rax, [rbx+80h]
0x18000cca9  mov     r8d, [rax+0Ch]
0x18000ccad  test    r8d, r8d
0x18000ccb0  jz      short loc_18000CCC2
0x18000ccb2  lea     rdx, aLinkageX; "  Linkage...........%x\n"
0x18000ccb9  mov     ecx, r13d
0x18000ccbc  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000ccc2  mov     r8, [rbx+80h]
0x18000ccc9  lea     rdx, aTimestampLowpa; "  TimeStamp:LowPart.0x%x\n"
0x18000ccd0  mov     ecx, r13d
0x18000ccd3  mov     r8d, [r8+10h]
0x18000ccd7  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000ccdd  mov     r8, [rbx+80h]
0x18000cce4  lea     rdx, aTimestampHipar; "  TimeStamp:HiPart..0x%x\n"
0x18000cceb  mov     ecx, r13d
0x18000ccee  mov     r8d, [r8+14h]
0x18000ccf2  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000ccf8  mov     rcx, [rbx+80h]
0x18000ccff  lea     rdx, [rsp+0A8h+lpsz]; lplpsz
0x18000cd07  add     rcx, 18h; rclsid
0x18000cd0b  mov     [rsp+0A8h+lpsz], rsi
0x18000cd13  call    cs:__imp_StringFromCLSID
0x18000cd19  test    eax, eax
0x18000cd1b  jnz     short loc_18000CD5A
0x18000cd1d  lea     rdx, aGuid; "  Guid.............."
0x18000cd24  mov     ecx, r13d
0x18000cd27  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000cd2d  mov     rcx, [rsp+0A8h+lpsz]; lpWideCharStr
0x18000cd35  mov     edx, edi; int
0x18000cd37  call    ?TranslateAndLog@@YAXPEAGH@Z; TranslateAndLog(ushort *,int)
0x18000cd3c  lea     rdx, asc_1800266E4; "\n"
0x18000cd43  mov     ecx, r13d
0x18000cd46  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000cd4c  mov     rcx, [rsp+0A8h+lpsz]; pv
0x18000cd54  call    cs:__imp_CoTaskMemFree
0x18000cd5a  mov     r8, [rbx+80h]
0x18000cd61  lea     rdx, aFlags0xX; "  Flags.............0x%x\n"
0x18000cd68  mov     ecx, r13d
0x18000cd6b  mov     r8d, [r8+2Ch]
0x18000cd6f  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000cd75  cmp     [rbx+70h], rsi
0x18000cd79  jz      short loc_18000CD83
0x18000cd7b  mov     rcx, rbx; this
0x18000cd7e  call    ?DumpSingleWnode@CWMIDataBlock@@IEAAXXZ; CWMIDataBlock::DumpSingleWnode(void)
0x18000cd83  cmp     [rbx+78h], rsi
0x18000cd87  jz      short loc_18000CD91
0x18000cd89  mov     rcx, rbx; this
0x18000cd8c  call    ?DumpAllWnode@CWMIDataBlock@@IEAAXXZ; CWMIDataBlock::DumpAllWnode(void)
0x18000cd91  mov     r15, [rbx+80h]
0x18000cd98  test    r15, r15
0x18000cd9b  jz      loc_18000CE70
0x18000cda1  mov     r15d, [r15]
0x18000cda4  lea     eax, [r15+100h]
0x18000cdab  mov     ecx, eax
0x18000cdad  mov     edi, eax
0x18000cdaf  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000cdb5  mov     r14, rax
0x18000cdb8  test    rax, rax
0x18000cdbb  jz      loc_18000CE70
0x18000cdc1  mov     r8d, r15d
0x18000cdc4  lea     rdx, aWritingOutBuff; "Writing out buffer, total size to write"...
0x18000cdcb  mov     ecx, r13d
0x18000cdce  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000cdd4  mov     r8d, edi; Size
0x18000cdd7  xor     edx, edx; Val
0x18000cdd9  mov     rcx, r14; void *
0x18000cddc  call    memset_0
0x18000cde1  mov     rdx, [rbx+80h]; Src
0x18000cde8  mov     r8d, r15d; Size
0x18000cdeb  mov     rcx, r14; void *
0x18000cdee  call    memcpy_0
0x18000cdf3  mov     rbp, r14
0x18000cdf6  mov     r12d, esi
0x18000cdf9  test    r15d, r15d
0x18000cdfc  jz      short loc_18000CE67
0x18000cdfe  movzx   ecx, byte ptr [rbp+8]
0x18000ce02  movzx   edx, byte ptr [rbp+7]
0x18000ce06  movzx   eax, byte ptr [rbp+9]
0x18000ce0a  movzx   r10d, byte ptr [rbp+6]
0x18000ce0f  movzx   r11d, byte ptr [rbp+5]
0x18000ce14  movzx   ebx, byte ptr [rbp+4]
0x18000ce18  movzx   edi, byte ptr [rbp+3]
0x18000ce1c  movzx   esi, byte ptr [rbp+2]
0x18000ce20  movzx   r9d, byte ptr [rbp+1]
0x18000ce25  movzx   r8d, byte ptr [rbp+0]
0x18000ce2a  mov     [rsp+0A8h+var_50], eax
0x18000ce2e  mov     [rsp+0A8h+var_58], ecx
0x18000ce32  mov     ecx, r13d
0x18000ce35  mov     [rsp+0A8h+var_60], edx
0x18000ce39  lea     rdx, a02x02x02x02x02; "  %02x %02x %02x %02x %02x %02x %02x %0"...
0x18000ce40  mov     [rsp+0A8h+var_68], r10d
0x18000ce45  mov     [rsp+0A8h+var_70], r11d
0x18000ce4a  mov     [rsp+0A8h+var_78], ebx
0x18000ce4e  mov     [rsp+0A8h+var_80], edi
0x18000ce52  mov     [rsp+0A8h+var_88], esi
0x18000ce56  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000ce5c  add     rbp, r13
0x18000ce5f  add     r12d, r13d
0x18000ce62  cmp     r12d, r15d
0x18000ce65  jb      short loc_18000CDFE
0x18000ce67  mov     rcx, r14
0x18000ce6a  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000ce70  mov     eax, 8004101Dh
0x18000ce75  add     rsp, 68h
0x18000ce79  pop     r15
0x18000ce7b  pop     r14
0x18000ce7d  pop     r13
0x18000ce7f  pop     r12
0x18000ce81  pop     rdi
0x18000ce82  pop     rsi
0x18000ce83  pop     rbp
0x18000ce84  pop     rbx
0x18000ce85  retn
```
