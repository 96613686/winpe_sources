# GetContactDisplayAddress(Windows::ApplicationModel::Contacts::IContactAddress *,HSTRING__ * *)

- ea: `0x1801d7638`
- end: `0x1801d77e4`
- name: `?GetContactDisplayAddress@@YAJPEAUIContactAddress@Contacts@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1801d9db0`

## callees

- `0x1801d7638`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d76b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7702`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d774e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7796`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d77cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d76b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7702`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d774e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7796`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d77cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801d7693`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801d76e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801d7733`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801d777b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801d7693`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801d76e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801d7733`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801d777b`

## pseudocode

```c
__int64 __fastcall GetContactDisplayAddress(
        struct Windows::ApplicationModel::Contacts::IContactAddress *a1,
        HSTRING *a2)
{
  __int64 v3; // rax
  __int64 (__fastcall *v5)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  int v6; // ebx
  __int64 (__fastcall *v7)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  __int64 (__fastcall *v8)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  __int64 (__fastcall *v9)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  __int64 (__fastcall *v10)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  HSTRING string; // [rsp+50h] [rbp+28h] BYREF

  *a2 = 0;
  v3 = *(_QWORD *)a1;
  string = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(v3 + 48);
  WindowsDeleteString(0);
  string = 0;
  v6 = v5(a1, &string);
  if ( v6 >= 0 )
  {
    if ( WindowsIsStringEmpty(string) )
    {
      v7 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(*(_QWORD *)a1 + 64LL);
      WindowsDeleteString(string);
      string = 0;
      v6 = v7(a1, &string);
      if ( v6 >= 0 )
      {
        if ( WindowsIsStringEmpty(string) )
        {
          v8 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(*(_QWORD *)a1 + 112LL);
          WindowsDeleteString(string);
          string = 0;
          v6 = v8(a1, &string);
          if ( v6 >= 0 )
          {
            if ( WindowsIsStringEmpty(string) )
            {
              v9 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(*(_QWORD *)a1 + 80LL);
              WindowsDeleteString(string);
              string = 0;
              v6 = v9(a1, &string);
              if ( v6 >= 0 )
              {
                if ( WindowsIsStringEmpty(string) )
                {
                  v10 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(*(_QWORD *)a1 + 96LL);
                  WindowsDeleteString(string);
                  string = 0;
                  v6 = v10(a1, &string);
                }
              }
            }
          }
        }
      }
    }
  }
  *a2 = string;
  string = 0;
  WindowsDeleteString(0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801d7638  push    rbp
0x1801d763a  push    rbx
0x1801d763b  push    rsi
0x1801d763c  push    rdi
0x1801d763d  mov     rbp, rsp
0x1801d7640  sub     rsp, 28h
0x1801d7644  mov     qword ptr [rdx], 0
0x1801d764b  mov     rdi, rcx
0x1801d764e  mov     rax, [rcx]
0x1801d7651  mov     rsi, rdx
0x1801d7654  xor     ecx, ecx; string
0x1801d7656  mov     [rbp+string], 0
0x1801d765e  mov     rbx, [rax+30h]
0x1801d7662  call    cs:__imp_WindowsDeleteString
0x1801d7669  nop     dword ptr [rax+rax+00h]
0x1801d766e  lea     rdx, [rbp+string]
0x1801d7672  mov     [rbp+string], 0
0x1801d767a  mov     rcx, rdi
0x1801d767d  mov     rax, rbx
0x1801d7680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7685  mov     ebx, eax
0x1801d7687  test    eax, eax
0x1801d7689  js      loc_1801D77BB
0x1801d768f  mov     rcx, [rbp+string]; string
0x1801d7693  call    cs:__imp_WindowsIsStringEmpty
0x1801d769a  nop     dword ptr [rax+rax+00h]
0x1801d769f  test    eax, eax
0x1801d76a1  jz      loc_1801D77BB
0x1801d76a7  mov     rax, [rdi]
0x1801d76aa  mov     rcx, [rbp+string]; string
0x1801d76ae  mov     rbx, [rax+40h]
0x1801d76b2  call    cs:__imp_WindowsDeleteString
0x1801d76b9  nop     dword ptr [rax+rax+00h]
0x1801d76be  lea     rdx, [rbp+string]
0x1801d76c2  mov     [rbp+string], 0
0x1801d76ca  mov     rcx, rdi
0x1801d76cd  mov     rax, rbx
0x1801d76d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d76d5  mov     ebx, eax
0x1801d76d7  test    eax, eax
0x1801d76d9  js      loc_1801D77BB
0x1801d76df  mov     rcx, [rbp+string]; string
0x1801d76e3  call    cs:__imp_WindowsIsStringEmpty
0x1801d76ea  nop     dword ptr [rax+rax+00h]
0x1801d76ef  test    eax, eax
0x1801d76f1  jz      loc_1801D77BB
0x1801d76f7  mov     rax, [rdi]
0x1801d76fa  mov     rcx, [rbp+string]; string
0x1801d76fe  mov     rbx, [rax+70h]
0x1801d7702  call    cs:__imp_WindowsDeleteString
0x1801d7709  nop     dword ptr [rax+rax+00h]
0x1801d770e  lea     rdx, [rbp+string]
0x1801d7712  mov     [rbp+string], 0
0x1801d771a  mov     rcx, rdi
0x1801d771d  mov     rax, rbx
0x1801d7720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7725  mov     ebx, eax
0x1801d7727  test    eax, eax
0x1801d7729  js      loc_1801D77BB
0x1801d772f  mov     rcx, [rbp+string]; string
0x1801d7733  call    cs:__imp_WindowsIsStringEmpty
0x1801d773a  nop     dword ptr [rax+rax+00h]
0x1801d773f  test    eax, eax
0x1801d7741  jz      short loc_1801D77BB
0x1801d7743  mov     rax, [rdi]
0x1801d7746  mov     rcx, [rbp+string]; string
0x1801d774a  mov     rbx, [rax+50h]
0x1801d774e  call    cs:__imp_WindowsDeleteString
0x1801d7755  nop     dword ptr [rax+rax+00h]
0x1801d775a  lea     rdx, [rbp+string]
0x1801d775e  mov     [rbp+string], 0
0x1801d7766  mov     rcx, rdi
0x1801d7769  mov     rax, rbx
0x1801d776c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7771  mov     ebx, eax
0x1801d7773  test    eax, eax
0x1801d7775  js      short loc_1801D77BB
0x1801d7777  mov     rcx, [rbp+string]; string
0x1801d777b  call    cs:__imp_WindowsIsStringEmpty
0x1801d7782  nop     dword ptr [rax+rax+00h]
0x1801d7787  test    eax, eax
0x1801d7789  jz      short loc_1801D77BB
0x1801d778b  mov     rax, [rdi]
0x1801d778e  mov     rcx, [rbp+string]; string
0x1801d7792  mov     rbx, [rax+60h]
0x1801d7796  call    cs:__imp_WindowsDeleteString
0x1801d779d  nop     dword ptr [rax+rax+00h]
0x1801d77a2  lea     rdx, [rbp+string]
0x1801d77a6  mov     [rbp+string], 0
0x1801d77ae  mov     rcx, rdi
0x1801d77b1  mov     rax, rbx
0x1801d77b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d77b9  mov     ebx, eax
0x1801d77bb  mov     rax, [rbp+string]
0x1801d77bf  xor     ecx, ecx; string
0x1801d77c1  mov     [rsi], rax
0x1801d77c4  mov     [rbp+string], 0
0x1801d77cc  call    cs:__imp_WindowsDeleteString
0x1801d77d3  nop     dword ptr [rax+rax+00h]
0x1801d77d8  mov     eax, ebx
0x1801d77da  add     rsp, 28h
0x1801d77de  pop     rdi
0x1801d77df  pop     rsi
0x1801d77e0  pop     rbx
0x1801d77e1  pop     rbp
0x1801d77e2  retn
```
