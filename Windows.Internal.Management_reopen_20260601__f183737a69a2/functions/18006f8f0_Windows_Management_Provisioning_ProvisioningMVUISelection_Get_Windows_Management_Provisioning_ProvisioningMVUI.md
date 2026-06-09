# Windows::Management::Provisioning::ProvisioningMVUISelection::Get(Windows::Management::Provisioning::ProvisioningMVUIItem *)

- ea: `0x18006f8f0`
- end: `0x18006f9ea`
- name: `?Get@ProvisioningMVUISelection@Provisioning@Management@Windows@@UEAAJPEAUProvisioningMVUIItem@234@@Z`
- size: `250`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::ProvisioningMVUISelection *__hidden this, struct Windows::Management::Provisioning::ProvisioningMVUIItem *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a5c4`
- `0x18006f8f0`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006f997`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006f997`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f9cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f9cb`

## pseudocode

```c
__int64 __fastcall Windows::Management::Provisioning::ProvisioningMVUISelection::Get(
        Windows::Management::Provisioning::ProvisioningMVUISelection *this,
        HSTRING *a2)
{
  __int64 v2; // rcx
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // edi
  __int64 v9; // rdx
  const WCHAR *v10; // rcx
  HRESULT String; // eax
  PCNZWCH sourceString[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *((_QWORD *)this + 4);
  if ( !v2 )
  {
    v4 = -2147418113;
    v5 = 68;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\provisioningmvuistatus.cpp",
      (const char *)v4,
      (int)sourceString[0]);
    return v4;
  }
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 69;
    goto LABEL_3;
  }
  *(_OWORD *)sourceString = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v2 + 40LL))(v2, sourceString);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\provisioningmvuistatus.cpp",
      (const char *)(unsigned int)v6,
      (int)sourceString[0]);
    return v7;
  }
  v9 = -1;
  v10 = sourceString[1];
  *(_DWORD *)a2 = sourceString[0];
  do
    ++v9;
  while ( v10[v9] );
  String = WindowsCreateString(v10, v9, a2 + 1);
  v4 = String;
  if ( String >= 0 )
    v4 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\provisioningmvuistatus.cpp",
      (const char *)(unsigned int)String,
      (int)sourceString[0]);
  CoTaskMemFree((LPVOID)sourceString[1]);
  return v4;
}

```

## disassembly

```asm
0x18006f8f0  mov     [rsp+arg_0], rbx
0x18006f8f5  mov     [rsp+arg_8], rsi
0x18006f8fa  push    rdi
0x18006f8fb  sub     rsp, 30h
0x18006f8ff  mov     rcx, [rcx+20h]
0x18006f903  xor     esi, esi
0x18006f905  mov     rbx, rdx
0x18006f908  test    rcx, rcx
0x18006f90b  jnz     short loc_18006F92E
0x18006f90d  mov     ebx, 8000FFFFh
0x18006f912  lea     edx, [rsi+44h]; void *
0x18006f915  mov     rcx, [rsp+38h]; this
0x18006f91a  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006f921  mov     r9d, ebx; char *
0x18006f924  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f929  jmp     loc_18006F9D7
0x18006f92e  test    rbx, rbx
0x18006f931  jnz     short loc_18006F93F
0x18006f933  mov     ebx, 80070057h
0x18006f938  mov     edx, 45h ; 'E'
0x18006f93d  jmp     short loc_18006F915
0x18006f93f  xorps   xmm0, xmm0
0x18006f942  lea     rdx, [rsp+38h+sourceString]
0x18006f947  movups  xmmword ptr [rsp+38h+sourceString], xmm0; int
0x18006f94c  mov     rax, [rcx]
0x18006f94f  mov     rax, [rax+28h]
0x18006f953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f958  mov     edi, eax
0x18006f95a  test    eax, eax
0x18006f95c  jns     short loc_18006F97B
0x18006f95e  mov     rcx, [rsp+38h]; this
0x18006f963  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006f96a  mov     r9d, eax; char *
0x18006f96d  mov     edx, 48h ; 'H'; void *
0x18006f972  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f977  mov     eax, edi
0x18006f979  jmp     short loc_18006F9D9
0x18006f97b  mov     eax, dword ptr [rsp+38h+sourceString]
0x18006f97f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18006f983  mov     rcx, [rsp+38h+sourceString+8]; sourceString
0x18006f988  mov     [rbx], eax
0x18006f98a  inc     rdx; length
0x18006f98d  cmp     [rcx+rdx*2], si
0x18006f991  jnz     short loc_18006F98A
0x18006f993  lea     r8, [rbx+8]; string
0x18006f997  call    cs:__imp_WindowsCreateString
0x18006f99e  nop     dword ptr [rax+rax+00h]
0x18006f9a3  mov     ebx, eax
0x18006f9a5  test    eax, eax
0x18006f9a7  jns     short loc_18006F9C4
0x18006f9a9  mov     rcx, [rsp+38h]; this
0x18006f9ae  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006f9b5  mov     r9d, eax; char *
0x18006f9b8  mov     edx, 4Fh ; 'O'; void *
0x18006f9bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f9c2  jmp     short loc_18006F9C6
0x18006f9c4  mov     ebx, esi
0x18006f9c6  mov     rcx, [rsp+38h+sourceString+8]; pv
0x18006f9cb  call    cs:__imp_CoTaskMemFree
0x18006f9d2  nop     dword ptr [rax+rax+00h]
0x18006f9d7  mov     eax, ebx
0x18006f9d9  mov     rbx, [rsp+38h+arg_0]
0x18006f9de  mov     rsi, [rsp+38h+arg_8]
0x18006f9e3  add     rsp, 30h
0x18006f9e7  pop     rdi
0x18006f9e8  retn
```
