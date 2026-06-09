# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,NLInternal::IVoiceEnabledShellHost,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x14001fcf0`
- end: `0x14001fd4f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIVoiceEnabledShellHost@NLInternal@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14001fcc0`
- `0x14001fcf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001fd12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001fd12`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,NLInternal::IVoiceEnabledShellHost,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,NLInternal::IVoiceEnabledShellHost,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x14001fcf0  mov     [rsp+arg_0], rbx
0x14001fcf5  push    rdi
0x14001fcf6  sub     rsp, 20h
0x14001fcfa  mov     qword ptr [r8], 0
0x14001fd01  mov     ecx, 20h ; ' '; cb
0x14001fd06  mov     dword ptr [rdx], 0
0x14001fd0c  mov     rbx, r8
0x14001fd0f  mov     rdi, rdx
0x14001fd12  call    cs:__imp_CoTaskMemAlloc
0x14001fd18  mov     r8, rax
0x14001fd1b  test    rax, rax
0x14001fd1e  jnz     short loc_14001FD27
0x14001fd20  mov     eax, 8007000Eh
0x14001fd25  jmp     short loc_14001FD44
0x14001fd27  lea     rdx, [rsp+28h+arg_8]
0x14001fd2c  mov     [rsp+28h+arg_8], 0
0x14001fd34  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$0A@UIVoiceEnabledShellHost@NLInternal@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,NLInternal::IVoiceEnabledShellHost,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14001fd39  mov     dword ptr [rdi], 2
0x14001fd3f  xor     eax, eax
0x14001fd41  mov     [rbx], r8
0x14001fd44  mov     rbx, [rsp+28h+arg_0]
0x14001fd49  add     rsp, 20h
0x14001fd4d  pop     rdi
0x14001fd4e  retn
```
