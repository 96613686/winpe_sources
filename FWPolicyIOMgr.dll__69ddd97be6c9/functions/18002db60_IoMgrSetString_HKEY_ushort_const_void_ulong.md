# IoMgrSetString(HKEY__ *,ushort const *,void *,ulong)

- ea: `0x18002db60`
- end: `0x18002dca7`
- name: `?IoMgrSetString@@YAJPEAUHKEY__@@PEBGPEAXK@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, _WORD *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003b94`
- `0x1800042c4`
- `0x18001e9ac`
- `0x18002db60`

## import_xrefs

- `fwbase!FwRegDeleteValue` at `0x18002dbde`
- `fwbase!FwRegDeleteValue` at `0x18002dbde`
- `fwbase!FwRegSetString` at `0x18002dc63`
- `fwbase!FwRegSetString` at `0x18002dc63`

## pseudocode

```c
__int64 __fastcall IoMgrSetString(HKEY a1, const unsigned __int16 *a2, _WORD *a3, unsigned int a4)
{
  unsigned __int64 v4; // rbx
  LPCOLESTR v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r9

  v4 = a4;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 299, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( (_DWORD)v4 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v9 = FwRegDeleteValue(a1, 0, a2);
    v10 = v9;
    if ( v9 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v11 = 300;
LABEL_25:
        v12 = (unsigned int)v9;
        goto LABEL_26;
      }
    }
    return v10;
  }
  if ( (v4 & 1) != 0 )
  {
    v12 = 2147942487LL;
    v10 = -2147024809;
    if ( v8 == (LPCOLESTR)&WPP_GLOBAL_Control || (v8[14] & 1) == 0 )
      return v10;
    v11 = 301;
    goto LABEL_26;
  }
  if ( a3[(v4 >> 1) - 1] )
  {
    v12 = 2147942487LL;
    v10 = -2147024809;
    if ( v8 == (LPCOLESTR)&WPP_GLOBAL_Control || (v8[14] & 1) == 0 )
      return v10;
    v11 = 302;
LABEL_26:
    WPP_SF_d(*((_QWORD *)v8 + 2), v11, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v12);
    return v10;
  }
  v9 = FwRegSetString(a1, 0, a2, a3);
  v10 = v9;
  if ( v9 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = 303;
      goto LABEL_25;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18002db60  push    rbx
0x18002db62  push    rbp
0x18002db63  push    rsi
0x18002db64  push    r12
0x18002db66  push    r13
0x18002db68  push    r14
0x18002db6a  push    r15
0x18002db6c  sub     rsp, 20h
0x18002db70  mov     ebx, r9d
0x18002db73  mov     rsi, r8
0x18002db76  mov     r14, rdx
0x18002db79  mov     rbp, rcx
0x18002db7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db83  lea     r12, WPP_GLOBAL_Control
0x18002db8a  lea     r13, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002db91  cmp     rcx, r12
0x18002db94  jz      short loc_18002DBB4
0x18002db96  test    byte ptr [rcx+1Ch], 8
0x18002db9a  jz      short loc_18002DBB4
0x18002db9c  mov     rcx, [rcx+10h]
0x18002dba0  mov     edx, 12Bh
0x18002dba5  mov     r8, r13
0x18002dba8  call    WPP_SF_
0x18002dbad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dbb4  xor     r15d, r15d
0x18002dbb7  test    rbp, rbp
0x18002dbba  jnz     short loc_18002DBC8
0x18002dbbc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002dbc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dbc8  test    rsi, rsi
0x18002dbcb  jnz     short loc_18002DC0F
0x18002dbcd  test    ebx, ebx
0x18002dbcf  jz      short loc_18002DBD6
0x18002dbd1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002dbd6  mov     r8, r14
0x18002dbd9  xor     edx, edx
0x18002dbdb  mov     rcx, rbp
0x18002dbde  call    cs:__imp_FwRegDeleteValue
0x18002dbe4  mov     ebx, eax
0x18002dbe6  test    eax, eax
0x18002dbe8  jns     loc_18002DC95
0x18002dbee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dbf5  cmp     rcx, r12
0x18002dbf8  jz      loc_18002DC95
0x18002dbfe  test    byte ptr [rcx+1Ch], 1
0x18002dc02  jz      loc_18002DC95
0x18002dc08  mov     edx, 12Ch
0x18002dc0d  jmp     short loc_18002DC86
0x18002dc0f  test    bl, 1
0x18002dc12  jz      short loc_18002DC2F
0x18002dc14  mov     r9d, 80070057h
0x18002dc1a  mov     ebx, r9d
0x18002dc1d  cmp     rcx, r12
0x18002dc20  jz      short loc_18002DC95
0x18002dc22  test    byte ptr [rcx+1Ch], 1
0x18002dc26  jz      short loc_18002DC95
0x18002dc28  mov     edx, 12Dh
0x18002dc2d  jmp     short loc_18002DC89
0x18002dc2f  mov     rax, rbx
0x18002dc32  shr     rax, 1
0x18002dc35  cmp     [rsi+rax*2-2], r15w
0x18002dc3b  jz      short loc_18002DC58
0x18002dc3d  mov     r9d, 80070057h
0x18002dc43  mov     ebx, r9d
0x18002dc46  cmp     rcx, r12
0x18002dc49  jz      short loc_18002DC95
0x18002dc4b  test    byte ptr [rcx+1Ch], 1
0x18002dc4f  jz      short loc_18002DC95
0x18002dc51  mov     edx, 12Eh
0x18002dc56  jmp     short loc_18002DC89
0x18002dc58  mov     r9, rsi
0x18002dc5b  mov     r8, r14
0x18002dc5e  xor     edx, edx
0x18002dc60  mov     rcx, rbp
0x18002dc63  call    cs:__imp_FwRegSetString
0x18002dc69  mov     ebx, eax
0x18002dc6b  test    eax, eax
0x18002dc6d  jns     short loc_18002DC95
0x18002dc6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc76  cmp     rcx, r12
0x18002dc79  jz      short loc_18002DC95
0x18002dc7b  test    byte ptr [rcx+1Ch], 1
0x18002dc7f  jz      short loc_18002DC95
0x18002dc81  mov     edx, 12Fh
0x18002dc86  mov     r9d, eax
0x18002dc89  mov     rcx, [rcx+10h]
0x18002dc8d  mov     r8, r13
0x18002dc90  call    WPP_SF_d
0x18002dc95  mov     eax, ebx
0x18002dc97  add     rsp, 20h
0x18002dc9b  pop     r15
0x18002dc9d  pop     r14
0x18002dc9f  pop     r13
0x18002dca1  pop     r12
0x18002dca3  pop     rsi
0x18002dca4  pop     rbp
0x18002dca5  pop     rbx
0x18002dca6  retn
```
