# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)

- ea: `0x1800313f4`
- end: `0x1800314a0`
- name: `??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `172`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180031c98`

## callees

- `0x180026937`
- `0x1800313f4`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180031438`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180031438`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v4; // rcx
  int v5; // edi
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v4 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  *a2 = 0;
  v7 = 0;
  v5 = RoActivateInstance(a1, &v7);
  if ( v5 >= 0 )
  {
    if ( !memcmp_0(&GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v7;
    }
    else
    {
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v7)(
             v7,
             &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800313f4  mov     [rsp+arg_0], rbx
0x1800313f9  push    rdi
0x1800313fa  sub     rsp, 20h
0x1800313fe  mov     rbx, rdx
0x180031401  mov     rdi, rcx
0x180031404  mov     rcx, [rdx]
0x180031407  test    rcx, rcx
0x18003140a  jz      short loc_180031420
0x18003140c  mov     qword ptr [rdx], 0
0x180031413  mov     rax, [rcx]
0x180031416  mov     rax, [rax+10h]
0x18003141a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003141f  nop
0x180031420  mov     qword ptr [rbx], 0
0x180031427  mov     [rsp+28h+arg_8], 0
0x180031430  lea     rdx, [rsp+28h+arg_8]
0x180031435  mov     rcx, rdi
0x180031438  call    cs:__imp_RoActivateInstance
0x18003143e  mov     edi, eax
0x180031440  test    eax, eax
0x180031442  js      short loc_180031493
0x180031444  mov     r8d, 10h; Size
0x18003144a  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180031451  lea     rcx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3; Buf1
0x180031458  call    memcmp_0
0x18003145d  mov     rcx, [rsp+28h+arg_8]
0x180031462  test    eax, eax
0x180031464  jnz     short loc_18003146B
0x180031466  mov     [rbx], rcx
0x180031469  jmp     short loc_180031493
0x18003146b  mov     rax, [rcx]
0x18003146e  mov     r8, rbx
0x180031471  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x180031478  mov     rax, [rax]
0x18003147b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031480  mov     edi, eax
0x180031482  mov     rcx, [rsp+28h+arg_8]
0x180031487  mov     rax, [rcx]
0x18003148a  mov     rax, [rax+10h]
0x18003148e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031493  mov     eax, edi
0x180031495  mov     rbx, [rsp+28h+arg_0]
0x18003149a  add     rsp, 20h
0x18003149e  pop     rdi
0x18003149f  retn
```
