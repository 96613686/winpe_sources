# IoMgrSetDword(HKEY__ *,ushort const *,void *,ulong)

- ea: `0x18002d720`
- end: `0x18002d825`
- name: `?IoMgrSetDword@@YAJPEAUHKEY__@@PEBGPEAXK@Z`
- size: `261`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003b94`
- `0x1800042c4`
- `0x18001e9ac`
- `0x18002d720`

## import_xrefs

- `fwbase!FwRegDeleteValue` at `0x18002d793`
- `fwbase!FwRegDeleteValue` at `0x18002d793`
- `fwbase!FwRegSetDWord` at `0x18002d7e2`
- `fwbase!FwRegSetDWord` at `0x18002d7e2`

## pseudocode

```c
__int64 __fastcall IoMgrSetDword(HKEY a1, const unsigned __int16 *a2, unsigned int *a3, unsigned int a4)
{
  LPCOLESTR v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r9

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 291, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
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
      v9 = FwRegSetDWord(a1, 0, a2, *a3);
      v10 = v9;
      if ( v9 < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v11 = 294;
          goto LABEL_21;
        }
      }
    }
    else
    {
      v10 = -2147024809;
      if ( v8 != (LPCOLESTR)&WPP_GLOBAL_Control && (v8[14] & 1) != 0 )
      {
        v11 = 293;
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
        v11 = 292;
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
0x18002d720  push    rbx
0x18002d722  push    rbp
0x18002d723  push    rsi
0x18002d724  push    rdi
0x18002d725  push    r14
0x18002d727  sub     rsp, 20h
0x18002d72b  mov     ebx, r9d
0x18002d72e  mov     rsi, r8
0x18002d731  mov     rbp, rdx
0x18002d734  mov     rdi, rcx
0x18002d737  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d73e  lea     r14, WPP_GLOBAL_Control
0x18002d745  cmp     rcx, r14
0x18002d748  jz      short loc_18002D76C
0x18002d74a  test    byte ptr [rcx+1Ch], 8
0x18002d74e  jz      short loc_18002D76C
0x18002d750  mov     rcx, [rcx+10h]
0x18002d754  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002d75b  mov     edx, 123h
0x18002d760  call    WPP_SF_
0x18002d765  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d76c  test    rdi, rdi
0x18002d76f  jnz     short loc_18002D77D
0x18002d771  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002d776  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d77d  test    rsi, rsi
0x18002d780  jnz     short loc_18002D7B8
0x18002d782  test    ebx, ebx
0x18002d784  jz      short loc_18002D78B
0x18002d786  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002d78b  mov     r8, rbp
0x18002d78e  xor     edx, edx
0x18002d790  mov     rcx, rdi
0x18002d793  call    cs:__imp_FwRegDeleteValue
0x18002d799  mov     ebx, eax
0x18002d79b  test    eax, eax
0x18002d79d  jns     short loc_18002D818
0x18002d79f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d7a6  cmp     rcx, r14
0x18002d7a9  jz      short loc_18002D818
0x18002d7ab  test    byte ptr [rcx+1Ch], 1
0x18002d7af  jz      short loc_18002D818
0x18002d7b1  mov     edx, 124h
0x18002d7b6  jmp     short loc_18002D805
0x18002d7b8  cmp     ebx, 4
0x18002d7bb  jnb     short loc_18002D7D7
0x18002d7bd  mov     ebx, 80070057h
0x18002d7c2  cmp     rcx, r14
0x18002d7c5  jz      short loc_18002D818
0x18002d7c7  test    byte ptr [rcx+1Ch], 1
0x18002d7cb  jz      short loc_18002D818
0x18002d7cd  mov     edx, 125h
0x18002d7d2  mov     r9d, ebx
0x18002d7d5  jmp     short loc_18002D808
0x18002d7d7  mov     r9d, [rsi]
0x18002d7da  mov     r8, rbp
0x18002d7dd  xor     edx, edx
0x18002d7df  mov     rcx, rdi
0x18002d7e2  call    cs:__imp_FwRegSetDWord
0x18002d7e8  mov     ebx, eax
0x18002d7ea  test    eax, eax
0x18002d7ec  jns     short loc_18002D818
0x18002d7ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d7f5  cmp     rcx, r14
0x18002d7f8  jz      short loc_18002D818
0x18002d7fa  test    byte ptr [rcx+1Ch], 1
0x18002d7fe  jz      short loc_18002D818
0x18002d800  mov     edx, 126h
0x18002d805  mov     r9d, eax
0x18002d808  mov     rcx, [rcx+10h]
0x18002d80c  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002d813  call    WPP_SF_d
0x18002d818  mov     eax, ebx
0x18002d81a  add     rsp, 20h
0x18002d81e  pop     r14
0x18002d820  pop     rdi
0x18002d821  pop     rsi
0x18002d822  pop     rbp
0x18002d823  pop     rbx
0x18002d824  retn
```
