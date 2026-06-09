# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Windows::Graphics::Internal::Printing::Workflow::IWorkflowSessionManager,Windows::Graphics::Internal::Printing::Workflow::IWorkflowSessionManager2>::GetIids(ulong *,_GUID * *)

- ea: `0x180017130`
- end: `0x1800171a9`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$CloakedIid@UIFastRundown@@@23@UIWorkflowSessionManager@Workflow@Printing@Internal@Graphics@Windows@@UIWorkflowSessionManager2@6789Windows@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800171b0`
- `0x1800171c0`

## callees

- `0x180017130`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017152`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017152`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Windows::Graphics::Internal::Printing::Workflow::IWorkflowSessionManager,Windows::Graphics::Internal::Printing::Workflow::IWorkflowSessionManager2>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_801156fd_7e96_4274_821e_96d94e0c2b1f;
  v5[3] = GUID_3ce4b87d_0abf_4e76_a557_a2082325270a;
  *a2 = 4;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180017130  mov     [rsp+arg_0], rbx
0x180017135  push    rdi
0x180017136  sub     rsp, 20h
0x18001713a  mov     qword ptr [r8], 0
0x180017141  mov     ecx, 40h ; '@'; cb
0x180017146  mov     dword ptr [rdx], 0
0x18001714c  mov     rbx, r8
0x18001714f  mov     rdi, rdx
0x180017152  call    cs:__imp_CoTaskMemAlloc
0x180017158  test    rax, rax
0x18001715b  jnz     short loc_180017164
0x18001715d  mov     eax, 8007000Eh
0x180017162  jmp     short loc_18001719E
0x180017164  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18001716b  movdqu  xmmword ptr [rax], xmm0
0x18001716f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180017176  movdqu  xmmword ptr [rax+10h], xmm1
0x18001717b  movups  xmm0, xmmword ptr cs:_GUID_801156fd_7e96_4274_821e_96d94e0c2b1f.Data1
0x180017182  movdqu  xmmword ptr [rax+20h], xmm0
0x180017187  movups  xmm1, xmmword ptr cs:_GUID_3ce4b87d_0abf_4e76_a557_a2082325270a.Data1
0x18001718e  movdqu  xmmword ptr [rax+30h], xmm1
0x180017193  mov     dword ptr [rdi], 4
0x180017199  mov     [rbx], rax
0x18001719c  xor     eax, eax
0x18001719e  mov     rbx, [rsp+28h+arg_0]
0x1800171a3  add     rsp, 20h
0x1800171a7  pop     rdi
0x1800171a8  retn
```
