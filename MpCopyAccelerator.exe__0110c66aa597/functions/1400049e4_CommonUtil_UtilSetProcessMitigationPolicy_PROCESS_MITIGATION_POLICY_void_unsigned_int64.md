# CommonUtil::UtilSetProcessMitigationPolicy(_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)

- ea: `0x1400049e4`
- end: `0x140004a54`
- name: `?UtilSetProcessMitigationPolicy@CommonUtil@@YAJW4_PROCESS_MITIGATION_POLICY@@PEAX_K@Z`
- size: `112`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, enum _PROCESS_MITIGATION_POLICY, void *, unsigned __int64)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140020b08`
- `0x140020c7c`
- `0x140020de0`
- `0x140020f38`
- `0x14002109c`
- `0x1400212c0`
- `0x140021788`
- `0x140021964`
- `0x140021abc`

## callees

- `0x14000493c`
- `0x1400049e4`
- `0x14001da70`

## import_xrefs

- `KERNEL32!SetProcessMitigationPolicy` at `0x1400049f6`
- `KERNEL32!SetProcessMitigationPolicy` at `0x1400049f6`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilSetProcessMitigationPolicy(CommonUtil *this, __int64 a2, void *a3)
{
  int LastFailure; // ebx

  LastFailure = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  if ( !(unsigned int)SetProcessMitigationPolicy(this) )
    LastFailure = HrGetLastFailure();
  if ( LastFailure >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      70,
      WPP_ea1c95212f5839c4f8de0ce952f1642b_Traceguids,
      (unsigned int)LastFailure);
  return (unsigned int)LastFailure;
}

```

## disassembly

```asm
0x1400049e4  push    rbx
0x1400049e6  sub     rsp, 20h
0x1400049ea  xor     ebx, ebx
0x1400049ec  test    rdx, rdx
0x1400049ef  jz      short loc_140004A49
0x1400049f1  test    r8, r8
0x1400049f4  jz      short loc_140004A49
0x1400049f6  call    cs:__imp_SetProcessMitigationPolicy
0x1400049fc  test    eax, eax
0x1400049fe  jnz     short loc_140004A07
0x140004a00  call    HrGetLastFailure
0x140004a05  mov     ebx, eax
0x140004a07  mov     ecx, ebx
0x140004a09  shr     ecx, 1Fh
0x140004a0c  test    cl, cl
0x140004a0e  jz      short loc_140004A45
0x140004a10  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a17  lea     rax, WPP_GLOBAL_Control
0x140004a1e  cmp     rcx, rax
0x140004a21  jz      short loc_140004A41
0x140004a23  test    byte ptr [rcx+1Ch], 1
0x140004a27  jz      short loc_140004A41
0x140004a29  mov     rcx, [rcx+10h]
0x140004a2d  lea     r8, WPP_ea1c95212f5839c4f8de0ce952f1642b_Traceguids
0x140004a34  mov     edx, 46h ; 'F'
0x140004a39  mov     r9d, ebx
0x140004a3c  call    WPP_SF_d
0x140004a41  mov     eax, ebx
0x140004a43  jmp     short loc_140004A4E
0x140004a45  xor     eax, eax
0x140004a47  jmp     short loc_140004A4E
0x140004a49  mov     eax, 80070057h
0x140004a4e  add     rsp, 20h
0x140004a52  pop     rbx
0x140004a53  retn
```
