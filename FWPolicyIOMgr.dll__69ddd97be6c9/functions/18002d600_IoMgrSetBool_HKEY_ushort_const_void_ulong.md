# IoMgrSetBool(HKEY__ *,ushort const *,void *,ulong)

- ea: `0x18002d600`
- end: `0x18002d710`
- name: `?IoMgrSetBool@@YAJPEAUHKEY__@@PEBGPEAXK@Z`
- size: `272`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, _DWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003b94`
- `0x1800042c4`
- `0x18001e9ac`
- `0x18002d600`

## import_xrefs

- `fwbase!FwRegDeleteValue` at `0x18002d673`
- `fwbase!FwRegDeleteValue` at `0x18002d673`
- `fwbase!FwRegSetDWord` at `0x18002d6cd`
- `fwbase!FwRegSetDWord` at `0x18002d6cd`

## pseudocode

```c
__int64 __fastcall IoMgrSetBool(HKEY a1, const unsigned __int16 *a2, _DWORD *a3, unsigned int a4)
{
  LPCOLESTR v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r9

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 295, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v8 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    if ( a4 >= 4 )
    {
      v9 = FwRegSetDWord(a1, 0, a2, *a3 != 0);
      v10 = v9;
      if ( v9 < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v11 = 298;
          goto LABEL_21;
        }
      }
    }
    else
    {
      v10 = -2147024809;
      if ( v8 != (LPCOLESTR)&WPP_GLOBAL_Control && (v8[14] & 1) != 0 )
      {
        v11 = 297;
        v12 = 2147942487LL;
LABEL_22:
        WPP_SF_d(*((_QWORD *)v8 + 2), v11, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v12);
      }
    }
  }
  else
  {
    if ( a4 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v9 = FwRegDeleteValue(a1, 0, a2);
    v10 = v9;
    if ( v9 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v11 = 296;
LABEL_21:
        v12 = (unsigned int)v9;
        goto LABEL_22;
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18002d600  push    rbx
0x18002d602  push    rbp
0x18002d603  push    rsi
0x18002d604  push    rdi
0x18002d605  push    r14
0x18002d607  sub     rsp, 20h
0x18002d60b  mov     ebx, r9d
0x18002d60e  mov     rsi, r8
0x18002d611  mov     rbp, rdx
0x18002d614  mov     rdi, rcx
0x18002d617  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d61e  lea     r14, WPP_GLOBAL_Control
0x18002d625  cmp     rcx, r14
0x18002d628  jz      short loc_18002D64C
0x18002d62a  test    byte ptr [rcx+1Ch], 8
0x18002d62e  jz      short loc_18002D64C
0x18002d630  mov     rcx, [rcx+10h]
0x18002d634  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002d63b  mov     edx, 127h
0x18002d640  call    WPP_SF_
0x18002d645  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d64c  test    rdi, rdi
0x18002d64f  jnz     short loc_18002D65D
0x18002d651  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002d656  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d65d  test    rsi, rsi
0x18002d660  jnz     short loc_18002D69C
0x18002d662  test    ebx, ebx
0x18002d664  jz      short loc_18002D66B
0x18002d666  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002d66b  mov     r8, rbp
0x18002d66e  xor     edx, edx
0x18002d670  mov     rcx, rdi
0x18002d673  call    cs:__imp_FwRegDeleteValue
0x18002d679  mov     ebx, eax
0x18002d67b  test    eax, eax
0x18002d67d  jns     loc_18002D703
0x18002d683  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d68a  cmp     rcx, r14
0x18002d68d  jz      short loc_18002D703
0x18002d68f  test    byte ptr [rcx+1Ch], 1
0x18002d693  jz      short loc_18002D703
0x18002d695  mov     edx, 128h
0x18002d69a  jmp     short loc_18002D6F0
0x18002d69c  cmp     ebx, 4
0x18002d69f  jnb     short loc_18002D6BB
0x18002d6a1  mov     ebx, 80070057h
0x18002d6a6  cmp     rcx, r14
0x18002d6a9  jz      short loc_18002D703
0x18002d6ab  test    byte ptr [rcx+1Ch], 1
0x18002d6af  jz      short loc_18002D703
0x18002d6b1  mov     edx, 129h
0x18002d6b6  mov     r9d, ebx
0x18002d6b9  jmp     short loc_18002D6F3
0x18002d6bb  xor     r9d, r9d
0x18002d6be  mov     r8, rbp
0x18002d6c1  cmp     [rsi], r9d
0x18002d6c4  mov     rcx, rdi
0x18002d6c7  setnz   r9b
0x18002d6cb  xor     edx, edx
0x18002d6cd  call    cs:__imp_FwRegSetDWord
0x18002d6d3  mov     ebx, eax
0x18002d6d5  test    eax, eax
0x18002d6d7  jns     short loc_18002D703
0x18002d6d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d6e0  cmp     rcx, r14
0x18002d6e3  jz      short loc_18002D703
0x18002d6e5  test    byte ptr [rcx+1Ch], 1
0x18002d6e9  jz      short loc_18002D703
0x18002d6eb  mov     edx, 12Ah
0x18002d6f0  mov     r9d, eax
0x18002d6f3  mov     rcx, [rcx+10h]
0x18002d6f7  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002d6fe  call    WPP_SF_d
0x18002d703  mov     eax, ebx
0x18002d705  add     rsp, 20h
0x18002d709  pop     r14
0x18002d70b  pop     rdi
0x18002d70c  pop     rsi
0x18002d70d  pop     rbp
0x18002d70e  pop     rbx
0x18002d70f  retn
```
