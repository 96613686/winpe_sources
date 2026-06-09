# ZTracer::Trace(ZTraceLevel,char const *,int,void const *,char const *)

- ea: `0x180002bd4`
- end: `0x180002d84`
- name: `?Trace@ZTracer@@QEAAXW4ZTraceLevel@@PEBDHPEBX1@Z`
- size: `432`
- prototype: `void __fastcall(ZTracer *, int, const char *, int, const void *, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000308c`

## callees

- `0x1800024bc`
- `0x180002bd4`
- `0x18000390c`
- `0x1800039d4`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002d0c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002d0c`

## pseudocode

```c
void __fastcall ZTracer::Trace(ZTracer *a1, int a2, const char *a3, int a4, const void *a5, const char *a6)
{
  const char *v6; // rdi
  int v11; // ecx
  __int64 *v12; // rdx
  char *v13; // rdx
  const char *v14; // r8

  v6 = ":";
  if ( *a6 )
    v6 = a6;
  if ( !*((_DWORD *)a1 + 6) )
    goto LABEL_30;
  v11 = a2;
  if ( !a2 )
  {
    if ( a5 == (const void *)-1LL )
    {
      if ( (Microsoft_Windows_ZTraceMapsEnableBits & 4) != 0 )
      {
        v12 = Error_LogNoThis;
        goto LABEL_26;
      }
      goto LABEL_30;
    }
    if ( (Microsoft_Windows_ZTraceMapsEnableBits & 4) == 0 )
      goto LABEL_30;
    v13 = Error_Log;
    goto LABEL_29;
  }
  v11 = a2 - 1;
  if ( a2 != 1 )
  {
    v11 = a2 - 2;
    if ( a2 == 2 )
    {
      if ( a5 == (const void *)-1LL )
      {
        if ( (Microsoft_Windows_ZTraceMapsEnableBits & 8) != 0 )
        {
          v12 = Warning_LogNoThis;
          goto LABEL_26;
        }
        goto LABEL_30;
      }
      if ( (Microsoft_Windows_ZTraceMapsEnableBits & 8) == 0 )
        goto LABEL_30;
      v13 = Warning_Log;
      goto LABEL_29;
    }
    if ( a2 != 3 )
    {
      if ( a5 == (const void *)-1LL )
      {
        if ( (Microsoft_Windows_ZTraceMapsEnableBits & 0x20) != 0 )
        {
          v12 = Noisy_LogNoThis;
LABEL_26:
          McTemplateU0ssd_EventWriteTransfer(v11, (_DWORD)v12, (_DWORD)a3, (_DWORD)v6, a4);
          goto LABEL_30;
        }
        goto LABEL_30;
      }
      if ( (Microsoft_Windows_ZTraceMapsEnableBits & 0x20) == 0 )
        goto LABEL_30;
      v13 = Noisy_Log;
LABEL_29:
      McTemplateU0sspd_EventWriteTransfer(v11, (_DWORD)v13, (_DWORD)a3, (_DWORD)v6, (char)a5, a4);
      goto LABEL_30;
    }
  }
  if ( a5 != (const void *)-1LL )
  {
    if ( (Microsoft_Windows_ZTraceMapsEnableBits & 0x10) == 0 )
      goto LABEL_30;
    v13 = Info_Log;
    goto LABEL_29;
  }
  if ( (Microsoft_Windows_ZTraceMapsEnableBits & 0x10) != 0 )
  {
    v12 = Info_LogNoThis;
    goto LABEL_26;
  }
LABEL_30:
  if ( s_fShouldSpewDebug && IsDebuggerPresent() )
  {
    if ( a2 )
    {
      v14 = "      ";
      if ( a2 == 2 )
        v14 = "[Z!W] ";
    }
    else
    {
      v14 = "[Z!E] ";
    }
    if ( a5 == (const void *)-1LL )
      ZTracer::DebugMsg(a1, "%s:%s: %s (%d)", v14, a3, v6, a4);
    else
      ZTracer::DebugMsg(a1, "%s:%s@%p: %s (%d)", v14, a3, a5, v6, a4);
  }
}

```

## disassembly

```asm
0x180002bd4  push    rbx
0x180002bd6  push    rbp
0x180002bd7  push    rsi
0x180002bd8  push    rdi
0x180002bd9  push    r14
0x180002bdb  push    r15
0x180002bdd  sub     rsp, 48h
0x180002be1  mov     rax, [rsp+78h+arg_28]
0x180002be9  lea     rdi, asc_180005594; ":"
0x180002bf0  mov     rbx, [rsp+78h+arg_20]
0x180002bf8  mov     esi, r9d
0x180002bfb  mov     rbp, r8
0x180002bfe  mov     r14d, edx
0x180002c01  mov     r15, rcx
0x180002c04  cmp     byte ptr [rax], 0
0x180002c07  cmovnz  rdi, rax
0x180002c0b  cmp     dword ptr [rcx+18h], 0
0x180002c0f  jz      loc_180002D03
0x180002c15  mov     ecx, edx
0x180002c17  test    edx, edx
0x180002c19  jz      loc_180002CBE
0x180002c1f  sub     ecx, 1
0x180002c22  jz      short loc_180002C66
0x180002c24  sub     ecx, 1
0x180002c27  jz      short loc_180002C94
0x180002c29  cmp     ecx, 1
0x180002c2c  jz      short loc_180002C66
0x180002c2e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002c32  jnz     short loc_180002C4D
0x180002c34  test    cs:Microsoft_Windows_ZTraceMapsEnableBits, 20h
0x180002c3b  jz      loc_180002D03
0x180002c41  lea     rdx, _Noisy_LogNoThis
0x180002c48  jmp     loc_180002CD4
0x180002c4d  test    cs:Microsoft_Windows_ZTraceMapsEnableBits, 20h
0x180002c54  jz      loc_180002D03
0x180002c5a  lea     rdx, _Noisy_Log
0x180002c61  jmp     loc_180002CF2
0x180002c66  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002c6a  jnz     short loc_180002C82
0x180002c6c  test    cs:Microsoft_Windows_ZTraceMapsEnableBits, 10h
0x180002c73  jz      loc_180002D03
0x180002c79  lea     rdx, _Info_LogNoThis
0x180002c80  jmp     short loc_180002CD4
0x180002c82  test    cs:Microsoft_Windows_ZTraceMapsEnableBits, 10h
0x180002c89  jz      short loc_180002D03
0x180002c8b  lea     rdx, _Info_Log
0x180002c92  jmp     short loc_180002CF2
0x180002c94  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002c98  jnz     short loc_180002CAC
0x180002c9a  test    cs:Microsoft_Windows_ZTraceMapsEnableBits, 8
0x180002ca1  jz      short loc_180002D03
0x180002ca3  lea     rdx, _Warning_LogNoThis
0x180002caa  jmp     short loc_180002CD4
0x180002cac  test    cs:Microsoft_Windows_ZTraceMapsEnableBits, 8
0x180002cb3  jz      short loc_180002D03
0x180002cb5  lea     rdx, _Warning_Log
0x180002cbc  jmp     short loc_180002CF2
0x180002cbe  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002cc2  jnz     short loc_180002CE2
0x180002cc4  test    cs:Microsoft_Windows_ZTraceMapsEnableBits, 4
0x180002ccb  jz      short loc_180002D03
0x180002ccd  lea     rdx, _Error_LogNoThis
0x180002cd4  mov     r9, rdi
0x180002cd7  mov     dword ptr [rsp+78h+var_58], esi
0x180002cdb  call    McTemplateU0ssd_EventWriteTransfer
0x180002ce0  jmp     short loc_180002D03
0x180002ce2  test    cs:Microsoft_Windows_ZTraceMapsEnableBits, 4
0x180002ce9  jz      short loc_180002D03
0x180002ceb  lea     rdx, _Error_Log
0x180002cf2  mov     dword ptr [rsp+78h+var_50], esi
0x180002cf6  mov     r9, rdi
0x180002cf9  mov     [rsp+78h+var_58], rbx
0x180002cfe  call    McTemplateU0sspd_EventWriteTransfer
0x180002d03  cmp     cs:?s_fShouldSpewDebug@@3HA, 0; int s_fShouldSpewDebug
0x180002d0a  jz      short loc_180002D77
0x180002d0c  call    cs:__imp_IsDebuggerPresent
0x180002d12  test    eax, eax
0x180002d14  jz      short loc_180002D77
0x180002d16  test    r14d, r14d
0x180002d19  jz      short loc_180002D33
0x180002d1b  cmp     r14d, 2
0x180002d1f  lea     r8, asc_1800055A8; "      "
0x180002d26  lea     rax, aZW; "[Z!W] "
0x180002d2d  cmovz   r8, rax
0x180002d31  jmp     short loc_180002D3A
0x180002d33  lea     r8, aZE; "[Z!E] "
0x180002d3a  mov     r9, rbp
0x180002d3d  mov     rcx, r15; this
0x180002d40  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002d44  jnz     short loc_180002D5D
0x180002d46  mov     dword ptr [rsp+78h+var_50], esi
0x180002d4a  lea     rdx, aSSSD; "%s:%s: %s (%d)"
0x180002d51  mov     [rsp+78h+var_58], rdi
0x180002d56  call    ?DebugMsg@ZTracer@@QEAAXPEBDZZ; ZTracer::DebugMsg(char const *,...)
0x180002d5b  jmp     short loc_180002D77
0x180002d5d  mov     [rsp+78h+var_48], esi
0x180002d61  lea     rdx, aSSPSD; "%s:%s@%p: %s (%d)"
0x180002d68  mov     [rsp+78h+var_50], rdi
0x180002d6d  mov     [rsp+78h+var_58], rbx
0x180002d72  call    ?DebugMsg@ZTracer@@QEAAXPEBDZZ; ZTracer::DebugMsg(char const *,...)
0x180002d77  add     rsp, 48h
0x180002d7b  pop     r15
0x180002d7d  pop     r14
0x180002d7f  pop     rdi
0x180002d80  pop     rsi
0x180002d81  pop     rbp
0x180002d82  pop     rbx
0x180002d83  retn
```
