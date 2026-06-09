# DSService::GetDSServiceNoLock(IDSService * *)

- ea: `0x180006634`
- end: `0x180006720`
- name: `?GetDSServiceNoLock@DSService@@SAJPEAPEAUIDSService@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(struct IDSService **)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000607c`
- `0x1800080f0`
- `0x1800081b0`

## callees

- `0x180003b84`
- `0x18000517c`
- `0x1800056d8`
- `0x180006634`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000668c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000668c`

## pseudocode

```c
__int64 __fastcall DSService::GetDSServiceNoLock(struct IDSService **a1)
{
  unsigned int v1; // edi
  struct IDSService *v3; // rbx
  __int64 v4; // rbx
  _BYTE *v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  *a1 = 0;
  v3 = (struct IDSService *)qword_180039C60;
  if ( qword_180039C60 )
    goto LABEL_6;
  v6 = operator new(0xF0u);
  v4 = (__int64)v6;
  if ( v6 )
  {
    v6[8] = 0;
    *(_QWORD *)v4 = &DSService::`vftable';
    *(_DWORD *)(v4 + 12) = 0;
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v4 + 16), 0, 0);
    *(_WORD *)(v4 + 56) = 0;
    *(_DWORD *)(v4 + 60) = 0;
    *(_QWORD *)(v4 + 64) = 0;
    *(_QWORD *)(v4 + 72) = 0;
    *(_QWORD *)(v4 + 80) = 0;
    v6 = (_BYTE *)v4;
    Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef((__int64 *)&v6);
    v6 = (_BYTE *)qword_180039C60;
    qword_180039C60 = v4;
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease((__int64 *)&v6);
  }
  else
  {
    v1 = -2147024882;
  }
  v3 = (struct IDSService *)qword_180039C60;
  if ( qword_180039C60 )
  {
LABEL_6:
    v6 = v3;
    Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef((__int64 *)&v6);
    v6 = 0;
    *a1 = v3;
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease((__int64 *)&v6);
  }
  return v1;
}

```

## disassembly

```asm
0x180006634  mov     [rsp+arg_8], rbx
0x180006639  mov     [rsp+arg_10], rsi
0x18000663e  push    rdi
0x18000663f  sub     rsp, 20h
0x180006643  xor     edi, edi
0x180006645  mov     rsi, rcx
0x180006648  mov     [rcx], rdi
0x18000664b  mov     rbx, cs:qword_180039C60
0x180006652  test    rbx, rbx
0x180006655  jnz     loc_1800066E9
0x18000665b  mov     ecx, 0F0h; Size
0x180006660  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006665  mov     [rsp+28h+arg_0], rax
0x18000666a  mov     rbx, rax
0x18000666d  test    rax, rax
0x180006670  jz      short loc_1800066D8
0x180006672  lea     rax, ??_7DSService@@6B@; const DSService::`vftable'
0x180006679  mov     [rbx+8], dil
0x18000667d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180006681  mov     [rbx], rax
0x180006684  xor     r8d, r8d; Flags
0x180006687  mov     [rbx+0Ch], edi
0x18000668a  xor     edx, edx; dwSpinCount
0x18000668c  call    cs:__imp_InitializeCriticalSectionEx
0x180006692  mov     [rbx+38h], di
0x180006696  mov     [rbx+3Ch], edi
0x180006699  mov     [rbx+40h], rdi
0x18000669d  mov     [rbx+48h], rdi
0x1800066a1  mov     [rbx+50h], rdi
0x1800066a5  test    rbx, rbx
0x1800066a8  jz      short loc_1800066D8
0x1800066aa  lea     rcx, [rsp+28h+arg_0]
0x1800066af  mov     [rsp+28h+arg_0], rbx
0x1800066b4  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x1800066b9  mov     rax, cs:qword_180039C60
0x1800066c0  lea     rcx, [rsp+28h+arg_0]
0x1800066c5  mov     [rsp+28h+arg_0], rax
0x1800066ca  mov     cs:qword_180039C60, rbx
0x1800066d1  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x1800066d6  jmp     short loc_1800066DD
0x1800066d8  mov     edi, 8007000Eh
0x1800066dd  mov     rbx, cs:qword_180039C60
0x1800066e4  test    rbx, rbx
0x1800066e7  jz      short loc_18000670E
0x1800066e9  lea     rcx, [rsp+28h+arg_0]
0x1800066ee  mov     [rsp+28h+arg_0], rbx
0x1800066f3  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x1800066f8  lea     rcx, [rsp+28h+arg_0]
0x1800066fd  mov     [rsp+28h+arg_0], 0
0x180006706  mov     [rsi], rbx
0x180006709  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18000670e  mov     rbx, [rsp+28h+arg_8]
0x180006713  mov     eax, edi
0x180006715  mov     rsi, [rsp+28h+arg_10]
0x18000671a  add     rsp, 20h
0x18000671e  pop     rdi
0x18000671f  retn
```
