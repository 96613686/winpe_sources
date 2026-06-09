# CMarshaledInterface::CMarshalStream::~CMarshalStream(void)

- ea: `0x180012508`
- end: `0x1800125a3`
- name: `??1CMarshalStream@CMarshaledInterface@@UEAA@XZ`
- size: `155`
- prototype: `void __fastcall(CMarshaledInterface::CMarshalStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800128c0`

## callees

- `0x180008bbc`
- `0x180012508`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012529`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012529`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180012537`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180012537`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180012570`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180012570`

## pseudocode

```c
void __fastcall CMarshaledInterface::CMarshalStream::~CMarshalStream(
        CMarshaledInterface::CMarshalStream *this,
        __int64 a2,
        __int64 a3)
{
  LPSTREAM *v3; // rbx
  bool v5; // zf
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  IStream *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  LPVOID ppv; // [rsp+30h] [rbp+8h] BYREF

  v3 = (LPSTREAM *)((char *)this + 16);
  v5 = *((_QWORD *)this + 2) == 0;
  *(_QWORD *)this = &CMarshaledInterface::CMarshalStream::`vftable';
  if ( !v5 )
  {
    if ( *((_DWORD *)this + 10) == GetCurrentThreadId() )
    {
      CoReleaseMarshalData(*v3);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v3, v8, v9);
    }
    else
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v6, v7);
      v10 = *v3;
      *v3 = 0;
      CoGetInterfaceAndReleaseStream(v10, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v11, v12);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 32, a2, a3);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v3, v13, v14);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180012508  mov     [rsp+arg_8], rbx
0x18001250d  push    rdi
0x18001250e  sub     rsp, 20h
0x180012512  lea     rbx, [rcx+10h]
0x180012516  mov     rdi, rcx
0x180012519  cmp     qword ptr [rbx], 0
0x18001251d  lea     rax, ??_7CMarshalStream@CMarshaledInterface@@6B@; const CMarshaledInterface::CMarshalStream::`vftable'
0x180012524  mov     [rcx], rax
0x180012527  jz      short loc_180012580
0x180012529  call    cs:__imp_GetCurrentThreadId
0x18001252f  cmp     [rdi+28h], eax
0x180012532  jnz     short loc_180012547
0x180012534  mov     rcx, [rbx]; pStm
0x180012537  call    cs:__imp_CoReleaseMarshalData
0x18001253d  mov     rcx, rbx
0x180012540  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012545  jmp     short loc_180012580
0x180012547  lea     rcx, [rsp+28h+ppv]
0x18001254c  mov     [rsp+28h+ppv], 0
0x180012555  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001255a  mov     rcx, [rbx]; pStm
0x18001255d  lea     r8, [rsp+28h+ppv]; ppv
0x180012562  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x180012569  mov     qword ptr [rbx], 0
0x180012570  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180012576  lea     rcx, [rsp+28h+ppv]
0x18001257b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012580  lea     rcx, [rdi+20h]
0x180012584  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012589  mov     rcx, rbx
0x18001258c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012591  mov     rbx, [rsp+28h+arg_8]
0x180012596  mov     dword ptr [rdi+0Ch], 0C0000001h
0x18001259d  add     rsp, 20h
0x1800125a1  pop     rdi
0x1800125a2  retn
```
