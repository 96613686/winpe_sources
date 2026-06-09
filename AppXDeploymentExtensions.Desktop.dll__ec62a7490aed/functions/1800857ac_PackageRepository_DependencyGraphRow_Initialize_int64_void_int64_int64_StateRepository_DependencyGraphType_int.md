# PackageRepository::DependencyGraphRow::Initialize(__int64,void *,__int64,__int64,StateRepository::DependencyGraphType,int)

- ea: `0x1800857ac`
- end: `0x180085891`
- name: `?Initialize@DependencyGraphRow@PackageRepository@@QEAAJ_JPEAX00W4DependencyGraphType@StateRepository@@H@Z`
- size: `229`
- prototype: `int __high(__int64, void *, __int64, __int64, enum StateRepository::DependencyGraphType, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180179ed4`
- `0x18017b6b4`

## callees

- `0x18000669c`
- `0x18001adb4`
- `0x1800857ac`
- `0x1800861b8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008585f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008585f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800857c4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800857c4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180085818`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180085818`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008582d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008582d`

## pseudocode

```c
__int64 __fastcall PackageRepository::DependencyGraphRow::Initialize(
        __int64 a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  unsigned int v10; // ebx
  __int64 v11; // rdx
  DWORD LengthSid; // esi
  HLOCAL v14; // rax
  void *v15; // rdx
  const char *v16; // r9
  int v17; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !IsValidSid(a3) )
  {
    v10 = -2147023559;
    v11 = 48;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\admin\\appmodel\\PackageRepository\\Inc\\External\\DependencyGraphRow.hpp",
      (const char *)v10,
      v17);
    return v10;
  }
  *(_QWORD *)a1 = a2;
  *(_QWORD *)(a1 + 48) = a4;
  *(_QWORD *)(a1 + 64) = a5;
  *(_DWORD *)(a1 + 72) = a6;
  *(_DWORD *)(a1 + 56) = 0;
  LengthSid = GetLengthSid(a3);
  v14 = LocalAlloc(0x40u, LengthSid);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    a1 + 104,
    v14);
  v15 = *(void **)(a1 + 104);
  if ( !v15 )
  {
    v10 = -2147024882;
    v11 = 58;
    goto LABEL_3;
  }
  if ( CopySid(LengthSid, v15, a3) )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x3B,
             (unsigned int)"onecore\\admin\\appmodel\\PackageRepository\\Inc\\External\\DependencyGraphRow.hpp",
             v16);
}

```

## disassembly

```asm
0x1800857ac  push    rbx
0x1800857ae  push    rbp
0x1800857af  push    rsi
0x1800857b0  push    rdi
0x1800857b1  sub     rsp, 28h
0x1800857b5  mov     rbx, rcx
0x1800857b8  mov     rsi, r9
0x1800857bb  mov     rcx, r8; pSid
0x1800857be  mov     rdi, r8
0x1800857c1  mov     rbp, rdx
0x1800857c4  call    cs:__imp_IsValidSid
0x1800857cb  nop     dword ptr [rax+rax+00h]
0x1800857d0  test    eax, eax
0x1800857d2  jnz     short loc_1800857F7
0x1800857d4  mov     ebx, 80070539h
0x1800857d9  lea     edx, [rax+30h]; void *
0x1800857dc  mov     rcx, [rsp+48h]; this
0x1800857e1  lea     r8, aOnecoreAdminAp_48; "onecore\\admin\\appmodel\\PackageReposi"...
0x1800857e8  mov     r9d, ebx; char *
0x1800857eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800857f0  mov     eax, ebx
0x1800857f2  jmp     loc_180085887
0x1800857f7  mov     rax, [rsp+48h+arg_20]
0x1800857fc  mov     rcx, rdi; pSid
0x1800857ff  mov     [rbx], rbp
0x180085802  mov     [rbx+30h], rsi
0x180085806  mov     [rbx+40h], rax
0x18008580a  mov     eax, [rsp+48h+arg_28]
0x18008580e  mov     [rbx+48h], eax
0x180085811  mov     dword ptr [rbx+38h], 0
0x180085818  call    cs:__imp_GetLengthSid
0x18008581f  nop     dword ptr [rax+rax+00h]
0x180085824  mov     edx, eax; uBytes
0x180085826  mov     ecx, 40h ; '@'; uFlags
0x18008582b  mov     esi, eax
0x18008582d  call    cs:__imp_LocalAlloc
0x180085834  nop     dword ptr [rax+rax+00h]
0x180085839  mov     rdx, rax
0x18008583c  lea     rcx, [rbx+68h]
0x180085840  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180085845  mov     rdx, [rbx+68h]; pDestinationSid
0x180085849  test    rdx, rdx
0x18008584c  jnz     short loc_18008585A
0x18008584e  mov     ebx, 8007000Eh
0x180085853  mov     edx, 3Ah ; ':'
0x180085858  jmp     short loc_1800857DC
0x18008585a  mov     r8, rdi; pSourceSid
0x18008585d  mov     ecx, esi; nDestinationSidLength
0x18008585f  call    cs:__imp_CopySid
0x180085866  nop     dword ptr [rax+rax+00h]
0x18008586b  test    eax, eax
0x18008586d  jnz     short loc_180085885
0x18008586f  mov     rcx, [rsp+48h]; this
0x180085874  lea     r8, aOnecoreAdminAp_48; "onecore\\admin\\appmodel\\PackageReposi"...
0x18008587b  lea     edx, [rax+3Bh]; void *
0x18008587e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180085883  jmp     short loc_180085887
0x180085885  xor     eax, eax
0x180085887  add     rsp, 28h
0x18008588b  pop     rdi
0x18008588c  pop     rsi
0x18008588d  pop     rbp
0x18008588e  pop     rbx
0x18008588f  retn
```
