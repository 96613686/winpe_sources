# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>)

- ea: `0x1400038ec`
- end: `0x14000398b`
- name: `??$ActivateInstance@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000829c`

## callees

- `0x1400038ec`
- `0x140006098`
- `0x140019394`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000391c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000391c`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(
        __int64 a1,
        __int64 *a2)
{
  int v4; // edi
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(a2);
  *a2 = 0;
  v6 = 0;
  v4 = RoActivateInstance(a1, &v6);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_9cb302b2_e79d_4beb_84c7_3abcb992df4e, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v6;
    }
    else
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(
             v6,
             &GUID_9cb302b2_e79d_4beb_84c7_3abcb992df4e,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400038ec  mov     [rsp+arg_0], rbx
0x1400038f1  push    rdi
0x1400038f2  sub     rsp, 20h
0x1400038f6  mov     rbx, rdx
0x1400038f9  mov     rdi, rcx
0x1400038fc  mov     rcx, rdx
0x1400038ff  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x140003904  mov     qword ptr [rbx], 0
0x14000390b  mov     [rsp+28h+arg_8], 0
0x140003914  lea     rdx, [rsp+28h+arg_8]
0x140003919  mov     rcx, rdi
0x14000391c  call    cs:__imp_RoActivateInstance
0x140003923  nop     dword ptr [rax+rax+00h]
0x140003928  mov     edi, eax
0x14000392a  test    eax, eax
0x14000392c  js      short loc_14000397D
0x14000392e  mov     r8d, 10h; Size
0x140003934  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x14000393b  lea     rcx, _GUID_9cb302b2_e79d_4beb_84c7_3abcb992df4e; Buf1
0x140003942  call    memcmp_0
0x140003947  mov     rcx, [rsp+28h+arg_8]
0x14000394c  test    eax, eax
0x14000394e  jnz     short loc_140003955
0x140003950  mov     [rbx], rcx
0x140003953  jmp     short loc_14000397D
0x140003955  mov     rax, [rcx]
0x140003958  mov     r8, rbx
0x14000395b  lea     rdx, _GUID_9cb302b2_e79d_4beb_84c7_3abcb992df4e
0x140003962  mov     rax, [rax]
0x140003965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000396a  mov     edi, eax
0x14000396c  mov     rcx, [rsp+28h+arg_8]
0x140003971  mov     rax, [rcx]
0x140003974  mov     rax, [rax+10h]
0x140003978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000397d  mov     eax, edi
0x14000397f  mov     rbx, [rsp+28h+arg_0]
0x140003984  add     rsp, 20h
0x140003988  pop     rdi
0x140003989  retn
```
