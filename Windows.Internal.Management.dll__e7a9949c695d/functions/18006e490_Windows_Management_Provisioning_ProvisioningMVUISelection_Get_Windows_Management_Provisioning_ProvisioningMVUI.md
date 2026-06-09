# Windows::Management::Provisioning::ProvisioningMVUISelection::Get(Windows::Management::Provisioning::ProvisioningMVUIItem *)

- ea: `0x18006e490`
- end: `0x18006e57d`
- name: `?Get@ProvisioningMVUISelection@Provisioning@Management@Windows@@UEAAJPEAUProvisioningMVUIItem@234@@Z`
- size: `237`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::ProvisioningMVUISelection *__hidden this, struct Windows::Management::Provisioning::ProvisioningMVUIItem *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a2a4`
- `0x18006e490`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006e537`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006e537`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e565`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e565`

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
0x18006e490  mov     [rsp+arg_0], rbx
0x18006e495  mov     [rsp+arg_8], rsi
0x18006e49a  push    rdi
0x18006e49b  sub     rsp, 30h
0x18006e49f  mov     rcx, [rcx+20h]
0x18006e4a3  xor     esi, esi
0x18006e4a5  mov     rbx, rdx
0x18006e4a8  test    rcx, rcx
0x18006e4ab  jnz     short loc_18006E4CE
0x18006e4ad  mov     ebx, 8000FFFFh
0x18006e4b2  lea     edx, [rsi+44h]; void *
0x18006e4b5  mov     rcx, [rsp+38h]; this
0x18006e4ba  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006e4c1  mov     r9d, ebx; char *
0x18006e4c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e4c9  jmp     loc_18006E56B
0x18006e4ce  test    rbx, rbx
0x18006e4d1  jnz     short loc_18006E4DF
0x18006e4d3  mov     ebx, 80070057h
0x18006e4d8  mov     edx, 45h ; 'E'
0x18006e4dd  jmp     short loc_18006E4B5
0x18006e4df  xorps   xmm0, xmm0
0x18006e4e2  lea     rdx, [rsp+38h+sourceString]
0x18006e4e7  movups  xmmword ptr [rsp+38h+sourceString], xmm0; int
0x18006e4ec  mov     rax, [rcx]
0x18006e4ef  mov     rax, [rax+28h]
0x18006e4f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e4f8  mov     edi, eax
0x18006e4fa  test    eax, eax
0x18006e4fc  jns     short loc_18006E51B
0x18006e4fe  mov     rcx, [rsp+38h]; this
0x18006e503  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006e50a  mov     r9d, eax; char *
0x18006e50d  mov     edx, 48h ; 'H'; void *
0x18006e512  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e517  mov     eax, edi
0x18006e519  jmp     short loc_18006E56D
0x18006e51b  mov     eax, dword ptr [rsp+38h+sourceString]
0x18006e51f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18006e523  mov     rcx, [rsp+38h+sourceString+8]; sourceString
0x18006e528  mov     [rbx], eax
0x18006e52a  inc     rdx; length
0x18006e52d  cmp     [rcx+rdx*2], si
0x18006e531  jnz     short loc_18006E52A
0x18006e533  lea     r8, [rbx+8]; string
0x18006e537  call    cs:__imp_WindowsCreateString
0x18006e53d  mov     ebx, eax
0x18006e53f  test    eax, eax
0x18006e541  jns     short loc_18006E55E
0x18006e543  mov     rcx, [rsp+38h]; this
0x18006e548  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006e54f  mov     r9d, eax; char *
0x18006e552  mov     edx, 4Fh ; 'O'; void *
0x18006e557  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e55c  jmp     short loc_18006E560
0x18006e55e  mov     ebx, esi
0x18006e560  mov     rcx, [rsp+38h+sourceString+8]; pv
0x18006e565  call    cs:__imp_CoTaskMemFree
0x18006e56b  mov     eax, ebx
0x18006e56d  mov     rbx, [rsp+38h+arg_0]
0x18006e572  mov     rsi, [rsp+38h+arg_8]
0x18006e577  add     rsp, 30h
0x18006e57b  pop     rdi
0x18006e57c  retn
```
