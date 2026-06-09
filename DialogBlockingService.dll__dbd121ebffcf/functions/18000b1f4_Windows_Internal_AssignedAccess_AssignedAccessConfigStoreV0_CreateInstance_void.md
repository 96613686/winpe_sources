# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::CreateInstance(void)

- ea: `0x18000b1f4`
- end: `0x18000b2c4`
- name: `?CreateInstance@AssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@SA?AV?$unique_ptr@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@XZ`
- size: `208`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b3c4`
- `0x18000b518`
- `0x18000b8ac`

## callees

- `0x180001650`
- `0x18000b1f4`
- `0x18000b680`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b25f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b25f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2a3`

## pseudocode

```c
_QWORD *__fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::CreateInstance(_QWORD *a1)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rbx
  LPVOID v5; // rbx
  char v6; // al
  void *v7; // rcx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  v2 = operator new(0x20u);
  pv = 0;
  *v2 = &Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::`vftable';
  v2[1] = 0;
  v2[2] = 0;
  v2[3] = 0;
  if ( (int)Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(
              L"SOFTWARE\\Microsoft\\Windows Embedded\\Lockdown",
              0,
              &pv) >= 0 )
  {
    v5 = pv;
    v6 = 0;
    if ( pv )
    {
      v7 = (void *)v2[1];
      if ( v7 )
        CoTaskMemFree(v7);
      v6 = 1;
      v2[1] = v5;
      v2[3] = -1;
      v2[2] = -1;
    }
    if ( v6 )
    {
      v3 = v2;
      goto LABEL_5;
    }
  }
  else if ( pv )
  {
    CoTaskMemFree(pv);
  }
  v3 = 0;
  (*(void (__fastcall **)(_QWORD *, __int64))*v2)(v2, 1);
LABEL_5:
  *a1 = v3;
  return a1;
}

```

## disassembly

```asm
0x18000b1f4  mov     [rsp+arg_8], rbx
0x18000b1f9  mov     [rsp+arg_10], rsi
0x18000b1fe  push    rdi
0x18000b1ff  sub     rsp, 20h
0x18000b203  mov     rsi, rcx
0x18000b206  mov     ecx, 20h ; ' '; Size
0x18000b20b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b210  mov     rdi, rax
0x18000b213  mov     [rsp+28h+pv], 0
0x18000b21c  lea     rax, ??_7AssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@6B@; const Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::`vftable'
0x18000b223  xor     edx, edx
0x18000b225  lea     r8, [rsp+28h+pv]
0x18000b22a  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Embedded\\"...
0x18000b231  mov     [rdi], rax
0x18000b234  mov     qword ptr [rdi+8], 0
0x18000b23c  mov     qword ptr [rdi+10h], 0
0x18000b244  mov     qword ptr [rdi+18h], 0
0x18000b24c  call    ?GetRedirectedPathIfNeeded@PersistentLocationHelper@AssignedAccess@Internal@Windows@@SAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18000b251  test    eax, eax
0x18000b253  jns     short loc_18000B28E
0x18000b255  mov     rcx, [rsp+28h+pv]; pv
0x18000b25a  test    rcx, rcx
0x18000b25d  jz      short loc_18000B265
0x18000b25f  call    cs:__imp_CoTaskMemFree
0x18000b265  mov     rax, [rdi]
0x18000b268  xor     ebx, ebx
0x18000b26a  mov     rcx, rdi
0x18000b26d  mov     rax, [rax]
0x18000b270  lea     edx, [rbx+1]
0x18000b273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b278  mov     [rsi], rbx
0x18000b27b  mov     rax, rsi
0x18000b27e  mov     rbx, [rsp+28h+arg_8]
0x18000b283  mov     rsi, [rsp+28h+arg_10]
0x18000b288  add     rsp, 20h
0x18000b28c  pop     rdi
0x18000b28d  retn
0x18000b28e  mov     rbx, [rsp+28h+pv]
0x18000b293  xor     al, al
0x18000b295  test    rbx, rbx
0x18000b298  jz      short loc_18000B2BB
0x18000b29a  mov     rcx, [rdi+8]; pv
0x18000b29e  test    rcx, rcx
0x18000b2a1  jz      short loc_18000B2A9
0x18000b2a3  call    cs:__imp_CoTaskMemFree
0x18000b2a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b2ad  mov     [rdi+8], rbx
0x18000b2b1  mov     [rdi+18h], rax
0x18000b2b5  mov     [rdi+10h], rax
0x18000b2b9  mov     al, 1
0x18000b2bb  test    al, al
0x18000b2bd  jz      short loc_18000B265
0x18000b2bf  mov     rbx, rdi
0x18000b2c2  jmp     short loc_18000B278
```
