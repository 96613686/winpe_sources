# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IUserOperations,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180015180`
- end: `0x1800151ea`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIUserOperations@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180014a60`
- `0x180015180`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800151a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800151a2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IUserOperations,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IUserOperations,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180015180  mov     [rsp+arg_0], rbx
0x180015185  push    rdi
0x180015186  sub     rsp, 20h
0x18001518a  mov     qword ptr [r8], 0
0x180015191  mov     ecx, 30h ; '0'; cb
0x180015196  mov     dword ptr [rdx], 0
0x18001519c  mov     rbx, r8
0x18001519f  mov     rdi, rdx
0x1800151a2  call    cs:__imp_CoTaskMemAlloc
0x1800151a8  mov     r8, rax
0x1800151ab  test    rax, rax
0x1800151ae  jnz     short loc_1800151B7
0x1800151b0  mov     eax, 8007000Eh
0x1800151b5  jmp     short loc_1800151DF
0x1800151b7  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x1800151be  lea     rdx, [rsp+28h+arg_8]
0x1800151c3  mov     [rsp+28h+arg_8], 1
0x1800151cb  movdqu  xmmword ptr [rax], xmm0
0x1800151cf  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIUserOperations@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IUserOperations,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800151d4  mov     dword ptr [rdi], 3
0x1800151da  xor     eax, eax
0x1800151dc  mov     [rbx], r8
0x1800151df  mov     rbx, [rsp+28h+arg_0]
0x1800151e4  add     rsp, 20h
0x1800151e8  pop     rdi
0x1800151e9  retn
```
