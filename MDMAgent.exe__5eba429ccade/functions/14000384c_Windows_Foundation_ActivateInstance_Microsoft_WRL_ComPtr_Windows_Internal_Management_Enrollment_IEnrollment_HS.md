# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>)

- ea: `0x14000384c`
- end: `0x1400038e4`
- name: `??$ActivateInstance@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140007f34`

## callees

- `0x14000384c`
- `0x140005e94`
- `0x140018634`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000387c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000387c`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(
        __int64 a1,
        _QWORD *a2)
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
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v6)(
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
0x14000384c  mov     [rsp+arg_0], rbx
0x140003851  push    rdi
0x140003852  sub     rsp, 20h
0x140003856  mov     rbx, rdx
0x140003859  mov     rdi, rcx
0x14000385c  mov     rcx, rdx
0x14000385f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x140003864  mov     qword ptr [rbx], 0
0x14000386b  mov     [rsp+28h+arg_8], 0
0x140003874  lea     rdx, [rsp+28h+arg_8]
0x140003879  mov     rcx, rdi
0x14000387c  call    cs:__imp_RoActivateInstance
0x140003882  mov     edi, eax
0x140003884  test    eax, eax
0x140003886  js      short loc_1400038D7
0x140003888  mov     r8d, 10h; Size
0x14000388e  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x140003895  lea     rcx, _GUID_9cb302b2_e79d_4beb_84c7_3abcb992df4e; Buf1
0x14000389c  call    memcmp_0
0x1400038a1  mov     rcx, [rsp+28h+arg_8]
0x1400038a6  test    eax, eax
0x1400038a8  jnz     short loc_1400038AF
0x1400038aa  mov     [rbx], rcx
0x1400038ad  jmp     short loc_1400038D7
0x1400038af  mov     rax, [rcx]
0x1400038b2  mov     r8, rbx
0x1400038b5  lea     rdx, _GUID_9cb302b2_e79d_4beb_84c7_3abcb992df4e
0x1400038bc  mov     rax, [rax]
0x1400038bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038c4  mov     edi, eax
0x1400038c6  mov     rcx, [rsp+28h+arg_8]
0x1400038cb  mov     rax, [rcx]
0x1400038ce  mov     rax, [rax+10h]
0x1400038d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038d7  mov     eax, edi
0x1400038d9  mov     rbx, [rsp+28h+arg_0]
0x1400038de  add     rsp, 20h
0x1400038e2  pop     rdi
0x1400038e3  retn
```
