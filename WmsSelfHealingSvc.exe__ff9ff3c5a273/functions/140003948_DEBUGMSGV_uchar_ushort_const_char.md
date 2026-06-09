# DEBUGMSGV(uchar,ushort const *,char *)

- ea: `0x140003948`
- end: `0x140003aab`
- name: `?DEBUGMSGV@@YAXEPEBGPEAD@Z`
- size: `355`
- prototype: `void __fastcall(unsigned __int8, const unsigned __int16 *, va_list)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400036a0`
- `0x140003918`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003948`
- `0x140003c2c`
- `0x14000404c`
- `0x140004224`
- `0x140004288`
- `0x140004440`
- `0x14000ae32`
- `0x14000ae60`
- `0x14000aef0`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1400039de`
- `KERNEL32!IsDebuggerPresent` at `0x1400039de`

## string_xrefs

- `0x1400039bb`: `termsrv\wms\src\common\ehmlib\ehmlib.cpp`
- `0x1400039c2`: `level < (sizeof(*RtlpNumberOf(s_rgEventDescriptor)))`

## pseudocode

```c
void __fastcall DEBUGMSGV(unsigned __int8 a1, const unsigned __int16 *a2, va_list a3)
{
  __int64 v6; // rdx
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  __int64 v8; // rcx
  int v9; // ebx
  void *v10; // rcx
  int v11; // [rsp+30h] [rbp-2058h]
  int v12; // [rsp+38h] [rbp-2050h]
  unsigned __int64 v13; // [rsp+40h] [rbp-2048h] BYREF
  unsigned __int16 v14[4096]; // [rsp+50h] [rbp-2038h] BYREF

  memset_0(v14, 0, sizeof(v14));
  v13 = 0;
  if ( a1 < 6u )
  {
    if ( (int)__EHM_AddPrefixToDebugMsg(v14, v6, &v13, a2, a3) >= 0 )
    {
      v9 = v13;
      __EHM_EtwWrite(v8, v7, v14, v13 + 1);
      __EHM_MsiWrite(g_hMsi, v14);
      __EHM_FlatFileWrite(v10, v14, v9);
    }
  }
  else
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
      0x1F8u,
      L"DEBUGMSGV",
      L"CBRAEx",
      L"level < (sizeof(*RtlpNumberOf(s_rgEventDescriptor)))",
      -2147024809);
    if ( IsDebuggerPresent() )
    {
      v12 = -2147024809;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
        504,
        L"DEBUGMSGV",
        L"CBRAEx",
        L"level < (sizeof(*RtlpNumberOf(s_rgEventDescriptor)))",
        v12);
    }
    else
    {
      v11 = -2147024809;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
        504,
        L"DEBUGMSGV",
        L"CBRAEx",
        L"level < (sizeof(*RtlpNumberOf(s_rgEventDescriptor)))",
        v11);
    }
  }
}

```

## disassembly

```asm
0x140003948  mov     [rsp+arg_0], rbx
0x14000394d  push    rbp
0x14000394e  push    rsi
0x14000394f  push    rdi
0x140003950  push    r14
0x140003952  push    r15
0x140003954  mov     eax, 2060h
0x140003959  call    _alloca_probe
0x14000395e  sub     rsp, rax
0x140003961  mov     rax, cs:__security_cookie
0x140003968  xor     rax, rsp
0x14000396b  mov     [rsp+2088h+var_38], rax
0x140003973  mov     rsi, r8
0x140003976  mov     rdi, rdx
0x140003979  mov     bl, cl
0x14000397b  xor     edx, edx; Val
0x14000397d  mov     r8d, 2000h; Size
0x140003983  lea     rcx, [rsp+2088h+var_2038]; void *
0x140003988  call    memset_0
0x14000398d  mov     [rsp+2088h+var_2048], 0
0x140003996  cmp     bl, 6
0x140003999  jb      loc_140003A39
0x14000399f  mov     ebx, 80070057h
0x1400039a4  lea     r15, aCbraex; "CBRAEx"
0x1400039ab  lea     rbp, aDebugmsgv; "DEBUGMSGV"
0x1400039b2  mov     [rsp+2088h+var_2060], ebx; int
0x1400039b6  mov     edi, 1F8h
0x1400039bb  lea     rsi, aTermsrvWmsSrcC_1; "termsrv\\wms\\src\\common\\ehmlib\\ehml"...
0x1400039c2  lea     r14, aLevelSizeofRtl; "level < (sizeof(*RtlpNumberOf(s_rgEvent"...
0x1400039c9  mov     r9, r15; unsigned __int16 *
0x1400039cc  mov     r8, rbp; unsigned __int16 *
0x1400039cf  mov     [rsp+2088h+var_2068], r14; unsigned __int16 *
0x1400039d4  mov     edx, edi; unsigned int
0x1400039d6  mov     rcx, rsi; unsigned __int16 *
0x1400039d9  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400039de  call    cs:__imp_IsDebuggerPresent
0x1400039e4  test    eax, eax
0x1400039e6  jz      short loc_140003A14
0x1400039e8  mov     [rsp+2088h+var_2050], ebx
0x1400039ec  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400039f3  mov     [rsp+2088h+var_2058], r14
0x1400039f8  mov     r9d, edi
0x1400039fb  mov     qword ptr [rsp+2088h+var_2060], r15
0x140003a00  mov     r8, rsi
0x140003a03  mov     ecx, 2; unsigned __int8
0x140003a08  mov     [rsp+2088h+var_2068], rbp
0x140003a0d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140003a12  jmp     short loc_140003A84
0x140003a14  mov     dword ptr [rsp+2088h+var_2058], ebx
0x140003a18  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140003a1f  mov     qword ptr [rsp+2088h+var_2060], r14
0x140003a24  mov     r9, rbp
0x140003a27  mov     r8d, edi
0x140003a2a  mov     [rsp+2088h+var_2068], r15
0x140003a2f  mov     rdx, rsi
0x140003a32  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140003a37  jmp     short loc_140003A84
0x140003a39  mov     r9, rdi; unsigned __int16 *
0x140003a3c  mov     [rsp+2088h+var_2068], rsi; char *
0x140003a41  lea     r8, [rsp+2088h+var_2048]; unsigned __int64 *
0x140003a46  lea     rcx, [rsp+2088h+var_2038]; unsigned __int16 *
0x140003a4b  call    ?__EHM_AddPrefixToDebugMsg@@YAJPEAG_KPEA_KPEBGPEAD@Z; __EHM_AddPrefixToDebugMsg(ushort *,unsigned __int64,unsigned __int64 *,ushort const *,char *)
0x140003a50  test    eax, eax
0x140003a52  js      short loc_140003A84
0x140003a54  mov     rbx, [rsp+2088h+var_2048]
0x140003a59  lea     r8, [rsp+2088h+var_2038]; unsigned __int16 *
0x140003a5e  lea     r9, [rbx+1]; unsigned __int64
0x140003a62  call    ?__EHM_EtwWrite@@YAX_KPEBU_EVENT_DESCRIPTOR@@PEBG0@Z; __EHM_EtwWrite(unsigned __int64,_EVENT_DESCRIPTOR const *,ushort const *,unsigned __int64)
0x140003a67  mov     ecx, cs:?g_hMsi@@3KA; unsigned int
0x140003a6d  lea     rdx, [rsp+2088h+var_2038]; unsigned __int16 *
0x140003a72  call    ?__EHM_MsiWrite@@YAXKPEBG@Z; __EHM_MsiWrite(ulong,ushort const *)
0x140003a77  mov     r8, rbx; unsigned __int64
0x140003a7a  lea     rdx, [rsp+2088h+var_2038]; unsigned __int16 *
0x140003a7f  call    ?__EHM_FlatFileWrite@@YAXPEAXPEBG_K@Z; __EHM_FlatFileWrite(void *,ushort const *,unsigned __int64)
0x140003a84  mov     rcx, [rsp+2088h+var_38]
0x140003a8c  xor     rcx, rsp; StackCookie
0x140003a8f  call    __security_check_cookie
0x140003a94  mov     rbx, [rsp+2088h+arg_0]
0x140003a9c  add     rsp, 2060h
0x140003aa3  pop     r15
0x140003aa5  pop     r14
0x140003aa7  pop     rdi
0x140003aa8  pop     rsi
0x140003aa9  pop     rbp
0x140003aaa  retn
```
