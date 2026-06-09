# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)

- ea: `0x18000847c`
- end: `0x180008514`
- name: `??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011b80`
- `0x18001b7e8`

## callees

- `0x18000517c`
- `0x18000847c`
- `0x18002614c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800084ac`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800084ac`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
        __int64 a1,
        _QWORD *a2)
{
  int v4; // edi
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(a2);
  *a2 = 0;
  v6 = 0;
  v4 = RoActivateInstance(a1, &v6);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v6;
    }
    else
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v6)(
             v6,
             &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000847c  mov     [rsp+arg_0], rbx
0x180008481  push    rdi
0x180008482  sub     rsp, 20h
0x180008486  mov     rbx, rdx
0x180008489  mov     rdi, rcx
0x18000848c  mov     rcx, rdx
0x18000848f  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180008494  mov     qword ptr [rbx], 0
0x18000849b  mov     [rsp+28h+arg_8], 0
0x1800084a4  lea     rdx, [rsp+28h+arg_8]
0x1800084a9  mov     rcx, rdi
0x1800084ac  call    cs:__imp_RoActivateInstance
0x1800084b2  mov     edi, eax
0x1800084b4  test    eax, eax
0x1800084b6  js      short loc_180008507
0x1800084b8  mov     r8d, 10h; Size
0x1800084be  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800084c5  lea     rcx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3; Buf1
0x1800084cc  call    memcmp_0
0x1800084d1  mov     rcx, [rsp+28h+arg_8]
0x1800084d6  test    eax, eax
0x1800084d8  jnz     short loc_1800084DF
0x1800084da  mov     [rbx], rcx
0x1800084dd  jmp     short loc_180008507
0x1800084df  mov     rax, [rcx]
0x1800084e2  mov     r8, rbx
0x1800084e5  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x1800084ec  mov     rax, [rax]
0x1800084ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084f4  mov     edi, eax
0x1800084f6  mov     rcx, [rsp+28h+arg_8]
0x1800084fb  mov     rax, [rcx]
0x1800084fe  mov     rax, [rax+10h]
0x180008502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008507  mov     eax, edi
0x180008509  mov     rbx, [rsp+28h+arg_0]
0x18000850e  add     rsp, 20h
0x180008512  pop     rdi
0x180008513  retn
```
