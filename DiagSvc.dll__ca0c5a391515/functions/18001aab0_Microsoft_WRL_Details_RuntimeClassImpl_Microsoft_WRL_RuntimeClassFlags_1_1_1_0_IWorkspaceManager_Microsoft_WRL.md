# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IWorkspaceManager,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001aab0`
- end: `0x18001ab0f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIWorkspaceManager@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001aa80`
- `0x18001aab0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001aad2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001aad2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IWorkspaceManager,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,IWorkspaceManager,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18001aab0  mov     [rsp+arg_0], rbx
0x18001aab5  push    rdi
0x18001aab6  sub     rsp, 20h
0x18001aaba  mov     qword ptr [r8], 0
0x18001aac1  mov     ecx, 20h ; ' '; cb
0x18001aac6  mov     dword ptr [rdx], 0
0x18001aacc  mov     rbx, r8
0x18001aacf  mov     rdi, rdx
0x18001aad2  call    cs:__imp_CoTaskMemAlloc
0x18001aad8  mov     r8, rax
0x18001aadb  test    rax, rax
0x18001aade  jnz     short loc_18001AAE7
0x18001aae0  mov     eax, 8007000Eh
0x18001aae5  jmp     short loc_18001AB04
0x18001aae7  lea     rdx, [rsp+28h+arg_8]
0x18001aaec  mov     [rsp+28h+arg_8], 0
0x18001aaf4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIWorkspaceManager@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,IWorkspaceManager,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001aaf9  mov     dword ptr [rdi], 2
0x18001aaff  xor     eax, eax
0x18001ab01  mov     [rbx], r8
0x18001ab04  mov     rbx, [rsp+28h+arg_0]
0x18001ab09  add     rsp, 20h
0x18001ab0d  pop     rdi
0x18001ab0e  retn
```
