# CVaultIntegrityLevel::~CVaultIntegrityLevel(void)

- ea: `0x180011110`
- end: `0x1800111ba`
- name: `??1CVaultIntegrityLevel@@QEAA@XZ`
- size: `170`
- prototype: `void __fastcall(HANDLE *ThreadInformation)`
- caller_count: `21`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f7d0`
- `0x18000ff18`
- `0x180012ae0`
- `0x1800151d0`
- `0x18001ab50`
- `0x18001eda0`
- `0x180023c90`
- `0x180026a80`
- `0x18002d724`
- `0x1800398d0`
- `0x180039ea8`
- `0x180040944`
- `0x180040f30`
- `0x18004bc20`
- `0x18004bc52`
- `0x18004c0b2`
- `0x18004c370`
- `0x18004c792`
- `0x18004c8e5`
- `0x18004c8f7`
- `0x18004ca51`

## callees

- `0x180011110`
- `0x18003b7b0`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011153`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011153`
- `ntdll!NtSetInformationThread` at `0x18001113f`
- `ntdll!NtSetInformationThread` at `0x18001113f`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall CVaultIntegrityLevel::~CVaultIntegrityLevel(HANDLE *ThreadInformation)
{
  NTSTATUS v2; // eax

  if ( *ThreadInformation )
  {
    v2 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, ThreadInformation, 8u);
    if ( v2 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids,
        (unsigned int)v2);
    CloseHandle(*ThreadInformation);
    *ThreadInformation = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids);
  }
}

```

## disassembly

```asm
0x180011110  push    rbx
0x180011112  sub     rsp, 20h
0x180011116  cmp     qword ptr [rcx], 0
0x18001111a  mov     rbx, rcx
0x18001111d  jnz     short loc_180011125
0x18001111f  add     rsp, 20h
0x180011123  pop     rbx
0x180011124  retn
0x180011125  mov     r9d, 8; ThreadInformationLength
0x18001112b  mov     [rsp+28h+arg_0], rdi
0x180011130  mov     r8, rbx; ThreadInformation
0x180011133  mov     edx, 5; ThreadInformationClass
0x180011138  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18001113f  call    cs:__imp_NtSetInformationThread
0x180011145  lea     rdi, WPP_GLOBAL_Control
0x18001114c  test    eax, eax
0x18001114e  js      short loc_18001118E
0x180011150  mov     rcx, [rbx]; hObject
0x180011153  call    cs:__imp_CloseHandle
0x180011159  mov     qword ptr [rbx], 0
0x180011160  mov     rcx, cs:WPP_GLOBAL_Control
0x180011167  cmp     rcx, rdi
0x18001116a  mov     rdi, [rsp+28h+arg_0]
0x18001116f  jz      short loc_18001111F
0x180011171  test    byte ptr [rcx+1Ch], 8
0x180011175  jz      short loc_18001111F
0x180011177  mov     rcx, [rcx+10h]
0x18001117b  lea     r8, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids
0x180011182  mov     edx, 0Bh
0x180011187  call    WPP_SF_
0x18001118c  jmp     short loc_18001111F
0x18001118e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011195  cmp     rcx, rdi
0x180011198  jz      short loc_180011150
0x18001119a  test    byte ptr [rcx+1Ch], 2
0x18001119e  jz      short loc_180011150
0x1800111a0  mov     rcx, [rcx+10h]
0x1800111a4  lea     r8, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids
0x1800111ab  mov     edx, 0Ah
0x1800111b0  mov     r9d, eax
0x1800111b3  call    WPP_SF_d
0x1800111b8  jmp     short loc_180011150
```
