# CommonUtil::UtilGetProcessMitigationPolicy(void *,_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)

- ea: `0x14000496c`
- end: `0x1400049e1`
- name: `?UtilGetProcessMitigationPolicy@CommonUtil@@YAJPEAXW4_PROCESS_MITIGATION_POLICY@@0_K@Z`
- size: `117`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, void *, enum _PROCESS_MITIGATION_POLICY, void *, unsigned __int64)`
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140020b08`
- `0x140020c7c`
- `0x140020de0`
- `0x140020f38`
- `0x14002109c`
- `0x1400211ec`
- `0x1400212c0`
- `0x140021788`
- `0x140021964`
- `0x140021abc`

## callees

- `0x14000493c`
- `0x14000496c`
- `0x14001da70`

## import_xrefs

- `KERNEL32!GetProcessMitigationPolicy` at `0x140004983`
- `KERNEL32!GetProcessMitigationPolicy` at `0x140004983`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetProcessMitigationPolicy(CommonUtil *this, void *a2, __int64 a3, void *a4)
{
  int LastFailure; // ebx

  LastFailure = 0;
  if ( !this || !a3 || !a4 )
    return 2147942487LL;
  if ( !(unsigned int)GetProcessMitigationPolicy(this, a2) )
    LastFailure = HrGetLastFailure();
  if ( LastFailure >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      69,
      WPP_ea1c95212f5839c4f8de0ce952f1642b_Traceguids,
      (unsigned int)LastFailure);
  return (unsigned int)LastFailure;
}

```

## disassembly

```asm
0x14000496c  push    rbx
0x14000496e  sub     rsp, 20h
0x140004972  xor     ebx, ebx
0x140004974  test    rcx, rcx
0x140004977  jz      short loc_1400049D6
0x140004979  test    r8, r8
0x14000497c  jz      short loc_1400049D6
0x14000497e  test    r9, r9
0x140004981  jz      short loc_1400049D6
0x140004983  call    cs:__imp_GetProcessMitigationPolicy
0x140004989  test    eax, eax
0x14000498b  jnz     short loc_140004994
0x14000498d  call    HrGetLastFailure
0x140004992  mov     ebx, eax
0x140004994  mov     ecx, ebx
0x140004996  shr     ecx, 1Fh
0x140004999  test    cl, cl
0x14000499b  jz      short loc_1400049D2
0x14000499d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400049a4  lea     rax, WPP_GLOBAL_Control
0x1400049ab  cmp     rcx, rax
0x1400049ae  jz      short loc_1400049CE
0x1400049b0  test    byte ptr [rcx+1Ch], 1
0x1400049b4  jz      short loc_1400049CE
0x1400049b6  mov     rcx, [rcx+10h]
0x1400049ba  lea     r8, WPP_ea1c95212f5839c4f8de0ce952f1642b_Traceguids
0x1400049c1  mov     edx, 45h ; 'E'
0x1400049c6  mov     r9d, ebx
0x1400049c9  call    WPP_SF_d
0x1400049ce  mov     eax, ebx
0x1400049d0  jmp     short loc_1400049DB
0x1400049d2  xor     eax, eax
0x1400049d4  jmp     short loc_1400049DB
0x1400049d6  mov     eax, 80070057h
0x1400049db  add     rsp, 20h
0x1400049df  pop     rbx
0x1400049e0  retn
```
