# Microsoft::WRL::Details::MakeAndInitialize<CCredentialProviderSerialization,ICredProviderCredentialSerialization,_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION &>(ICredProviderCredentialSerialization * *,_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION &)

- ea: `0x140005c08`
- end: `0x140005d04`
- name: `??$MakeAndInitialize@VCCredentialProviderSerialization@@UICredProviderCredentialSerialization@@AEAU_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION@@@Details@WRL@Microsoft@@YAJPEAPEAUICredProviderCredentialSerialization@@AEAU_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(_QWORD *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001894c`

## callees

- `0x140003644`
- `0x140005c08`
- `0x140008104`
- `0x140008920`
- `0x14001e060`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140005c7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140005c7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140005c91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140005c91`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CCredentialProviderSerialization,ICredProviderCredentialSerialization,_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION &>(
        _QWORD *a1,
        int *a2)
{
  CCredentialProviderSerialization *v4; // rax
  CCredentialProviderSerialization *v6; // rax
  int v7; // ecx
  CCredentialProviderSerialization *v8; // rbx
  SIZE_T v9; // rcx
  LPVOID v10; // rax
  void *v11; // rcx
  void *v12; // rbp
  unsigned int v13; // edi
  CCredentialProviderSerialization *v14; // [rsp+50h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = (CCredentialProviderSerialization *)operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v4;
  if ( v4 )
  {
    v6 = CCredentialProviderSerialization::CCredentialProviderSerialization(v4);
    v7 = *a2;
    v8 = v6;
    v14 = 0;
    *((_DWORD *)v6 + 21) = v7;
    *(_OWORD *)((char *)v6 + 88) = *(_OWORD *)(a2 + 1);
    v9 = (unsigned int)a2[5];
    *((_DWORD *)v6 + 20) = v9;
    *((_DWORD *)v6 + 26) = 0;
    v10 = CoTaskMemAlloc(v9);
    v11 = (void *)*((_QWORD *)v8 + 9);
    v12 = v10;
    *((_QWORD *)v8 + 9) = 0;
    CoTaskMemFree(v11);
    *((_QWORD *)v8 + 9) = v12;
    if ( v12 )
    {
      memcpy_0(v12, *((const void **)a2 + 3), (unsigned int)a2[5]);
      v13 = (**(__int64 (__fastcall ***)(CCredentialProviderSerialization *, GUID *, _QWORD *))v8)(
              v8,
              &GUID_e86e9b83_bc3e_4f34_8e22_8cda6723295c,
              a1);
      (*(void (__fastcall **)(CCredentialProviderSerialization *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    else
    {
      (*(void (__fastcall **)(CCredentialProviderSerialization *))(*(_QWORD *)v8 + 16LL))(v8);
      v13 = -2147024882;
    }
    Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(&v14);
    return v13;
  }
  else
  {
    Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(&v14);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x140005c08  push    rbx
0x140005c0a  push    rbp
0x140005c0b  push    rsi
0x140005c0c  push    rdi
0x140005c0d  sub     rsp, 28h
0x140005c11  mov     rdi, rdx
0x140005c14  mov     qword ptr [rcx], 0
0x140005c1b  mov     rsi, rcx
0x140005c1e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140005c25  mov     ecx, 88h; unsigned __int64
0x140005c2a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140005c2f  mov     [rsp+48h+arg_0], rax
0x140005c34  test    rax, rax
0x140005c37  jnz     short loc_140005C4D
0x140005c39  lea     rcx, [rsp+48h+arg_0]
0x140005c3e  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(void)
0x140005c43  mov     eax, 8007000Eh
0x140005c48  jmp     loc_140005CFB
0x140005c4d  mov     rcx, rax; this
0x140005c50  call    ??0CCredentialProviderSerialization@@QEAA@XZ; CCredentialProviderSerialization::CCredentialProviderSerialization(void)
0x140005c55  mov     ecx, [rdi]
0x140005c57  mov     rbx, rax
0x140005c5a  mov     [rsp+48h+arg_0], 0
0x140005c63  mov     [rax+54h], ecx
0x140005c66  movups  xmm0, xmmword ptr [rdi+4]
0x140005c6a  movdqu  xmmword ptr [rax+58h], xmm0
0x140005c6f  mov     ecx, [rdi+14h]; cb
0x140005c72  mov     [rax+50h], ecx
0x140005c75  mov     dword ptr [rax+68h], 0
0x140005c7c  call    cs:__imp_CoTaskMemAlloc
0x140005c82  mov     rcx, [rbx+48h]; pv
0x140005c86  mov     rbp, rax
0x140005c89  mov     qword ptr [rbx+48h], 0
0x140005c91  call    cs:__imp_CoTaskMemFree
0x140005c97  mov     [rbx+48h], rbp
0x140005c9b  test    rbp, rbp
0x140005c9e  jz      short loc_140005CDB
0x140005ca0  mov     r8d, [rdi+14h]; Size
0x140005ca4  mov     rcx, rbp; void *
0x140005ca7  mov     rdx, [rdi+18h]; Src
0x140005cab  call    memcpy_0
0x140005cb0  mov     rax, [rbx]
0x140005cb3  lea     rdx, _GUID_e86e9b83_bc3e_4f34_8e22_8cda6723295c
0x140005cba  mov     r8, rsi
0x140005cbd  mov     rcx, rbx
0x140005cc0  mov     rax, [rax]
0x140005cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cc8  mov     rcx, [rbx]
0x140005ccb  mov     edi, eax
0x140005ccd  mov     rax, [rcx+10h]
0x140005cd1  mov     rcx, rbx
0x140005cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cd9  jmp     short loc_140005CEF
0x140005cdb  mov     rax, [rbx]
0x140005cde  mov     rcx, rbx
0x140005ce1  mov     rax, [rax+10h]
0x140005ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cea  mov     edi, 8007000Eh
0x140005cef  lea     rcx, [rsp+48h+arg_0]
0x140005cf4  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VCCredUIBrokerForNonAppContainersFailedMip@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CCredUIBrokerForNonAppContainersFailedMip,0>>(void)
0x140005cf9  mov     eax, edi
0x140005cfb  add     rsp, 28h
0x140005cff  pop     rdi
0x140005d00  pop     rsi
0x140005d01  pop     rbp
0x140005d02  pop     rbx
0x140005d03  retn
```
