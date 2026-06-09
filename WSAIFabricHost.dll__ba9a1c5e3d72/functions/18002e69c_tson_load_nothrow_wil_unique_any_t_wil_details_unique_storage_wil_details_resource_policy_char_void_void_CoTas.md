# tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::input_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x18002e69c`
- end: `0x18002e865`
- name: `??$load_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `457`
- prototype: `void __fastcall(tson::input_archive *this, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a550`

## callees

- `0x18002a3c4`
- `0x18002e69c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e733`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e7ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e806`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e733`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e7ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e806`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e7b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e7b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e741`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e814`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e741`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e814`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e721`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e7f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e849`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e721`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e7f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e849`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        void **a2)
{
  __int64 v2; // rbx
  char *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  _WORD *v9; // rdx
  unsigned __int16 v10; // cx
  unsigned __int64 v11; // rdi
  void *v12; // rcx
  void *v13; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int64 v15; // rax
  __int64 v16; // rbp
  HANDLE v17; // rax
  _QWORD *v18; // rax
  _QWORD *v19; // r15
  unsigned __int64 v20; // rdi
  _QWORD *v21; // rcx
  void *v22; // rcx
  void *v23; // rdi
  HANDLE v24; // rax
  void *v25; // rcx
  void *v26; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  if ( !*((_BYTE *)this + 25) )
  {
    v5 = (char *)this + 32;
    v6 = *((_QWORD *)this + 17);
    if ( v6 )
      v5 = &v5[4 * v6 - 4];
    else
      *v5 = 1;
    if ( *((_DWORD *)v5 + 1) != 1 && *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147023267;
    v7 = *(_QWORD *)this;
    v8 = *(unsigned __int16 **)(*(_QWORD *)this + 8LL);
    v9 = v8 + 1;
    if ( (unsigned __int64)(v8 + 1) > *(_QWORD *)(*(_QWORD *)this + 16LL) )
    {
      v10 = 0;
      *(_BYTE *)(v7 + 24) = 1;
    }
    else
    {
      v10 = *v8;
      *(_QWORD *)(v7 + 8) = v9;
    }
    v2 = v10;
  }
  if ( *a2 )
  {
    v11 = 0;
    if ( a2[2] )
    {
      do
      {
        v12 = (void *)*((_QWORD *)*a2 + v11);
        if ( v12 )
          CoTaskMemFree(v12);
        ++v11;
      }
      while ( v11 < (unsigned __int64)a2[2] );
    }
    v13 = *a2;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v13);
    *a2 = 0;
  }
  a2[1] = 0;
  a2[2] = 0;
  while ( v2 )
  {
    v26 = 0;
    --v2;
    tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(
      this,
      &v26);
    v15 = (unsigned __int64)a2[1];
    if ( (unsigned __int64)a2[2] < v15 )
      goto LABEL_35;
    if ( v15 )
    {
      v16 = 2 * v15;
      if ( 2 * v15 <= v15 )
        goto LABEL_32;
    }
    else
    {
      v16 = 10;
    }
    v17 = GetProcessHeap();
    v18 = HeapAlloc(v17, 0, 8 * v16);
    v19 = v18;
    if ( !v18 )
      goto LABEL_33;
    if ( *a2 )
    {
      v20 = 0;
      if ( a2[2] )
      {
        do
        {
          v21 = *a2;
          v19[v20] = *((_QWORD *)*a2 + v20);
          v21[v20] = 0;
          v22 = (void *)*((_QWORD *)*a2 + v20);
          if ( v22 )
            CoTaskMemFree(v22);
          ++v20;
        }
        while ( v20 < (unsigned __int64)a2[2] );
      }
      v23 = *a2;
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v23);
    }
    *a2 = v19;
    a2[1] = (void *)v16;
LABEL_32:
    LOBYTE(v18) = 1;
LABEL_33:
    if ( (_BYTE)v18 )
    {
LABEL_35:
      *((_QWORD *)*a2 + (_QWORD)a2[2]) = v26;
      v25 = 0;
      a2[2] = (char *)a2[2] + 1;
      goto LABEL_36;
    }
    v25 = v26;
LABEL_36:
    if ( v25 )
      CoTaskMemFree(v25);
  }
}

```

## disassembly

```asm
0x18002e69c  push    rbx
0x18002e69e  push    rbp
0x18002e69f  push    rsi
0x18002e6a0  push    rdi
0x18002e6a1  push    r14
0x18002e6a3  push    r15
0x18002e6a5  sub     rsp, 28h
0x18002e6a9  xor     ebx, ebx
0x18002e6ab  mov     rsi, rdx
0x18002e6ae  mov     r14, rcx
0x18002e6b1  cmp     [rcx+19h], bl
0x18002e6b4  jnz     short loc_18002E707
0x18002e6b6  lea     rax, [rcx+20h]
0x18002e6ba  mov     rcx, [rax+68h]
0x18002e6be  test    rcx, rcx
0x18002e6c1  jz      short loc_18002E6CD
0x18002e6c3  lea     rax, [rax+rcx*4]
0x18002e6c7  add     rax, 0FFFFFFFFFFFFFFFCh
0x18002e6cb  jmp     short loc_18002E6D0
0x18002e6cd  mov     byte ptr [rax], 1
0x18002e6d0  cmp     dword ptr [rax+4], 1
0x18002e6d4  jz      short loc_18002E6E4
0x18002e6d6  cmp     [r14+8], ebx
0x18002e6da  jl      short loc_18002E6E4
0x18002e6dc  mov     dword ptr [r14+8], 8007065Dh
0x18002e6e4  mov     rax, [r14]
0x18002e6e7  mov     rcx, [rax+8]
0x18002e6eb  lea     rdx, [rcx+2]
0x18002e6ef  cmp     rdx, [rax+10h]
0x18002e6f3  ja      short loc_18002E6FE
0x18002e6f5  movzx   ecx, word ptr [rcx]
0x18002e6f8  mov     [rax+8], rdx
0x18002e6fc  jmp     short loc_18002E704
0x18002e6fe  xor     ecx, ecx
0x18002e700  mov     byte ptr [rax+18h], 1
0x18002e704  movzx   ebx, cx
0x18002e707  cmp     qword ptr [rsi], 0
0x18002e70b  jz      short loc_18002E74E
0x18002e70d  xor     edi, edi
0x18002e70f  cmp     [rsi+10h], rdi
0x18002e713  jbe     short loc_18002E730
0x18002e715  mov     rax, [rsi]
0x18002e718  mov     rcx, [rax+rdi*8]; pv
0x18002e71c  test    rcx, rcx
0x18002e71f  jz      short loc_18002E727
0x18002e721  call    cs:__imp_CoTaskMemFree
0x18002e727  inc     rdi
0x18002e72a  cmp     rdi, [rsi+10h]
0x18002e72e  jb      short loc_18002E715
0x18002e730  mov     rdi, [rsi]
0x18002e733  call    cs:__imp_GetProcessHeap
0x18002e739  mov     r8, rdi; lpMem
0x18002e73c  xor     edx, edx; dwFlags
0x18002e73e  mov     rcx, rax; hHeap
0x18002e741  call    cs:__imp_HeapFree
0x18002e747  mov     qword ptr [rsi], 0
0x18002e74e  mov     qword ptr [rsi+8], 0
0x18002e756  mov     qword ptr [rsi+10h], 0
0x18002e75e  jmp     loc_18002E84F
0x18002e763  lea     rdx, [rsp+58h+arg_0]
0x18002e768  mov     [rsp+58h+arg_0], 0
0x18002e771  mov     rcx, r14; this
0x18002e774  dec     rbx
0x18002e777  call    ??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)
0x18002e77c  mov     rax, [rsi+8]
0x18002e780  cmp     [rsi+10h], rax
0x18002e784  jb      loc_18002E82E
0x18002e78a  test    rax, rax
0x18002e78d  jz      short loc_18002E79E
0x18002e78f  lea     rbp, [rax+rax]
0x18002e793  cmp     rbp, rax
0x18002e796  jbe     loc_18002E821
0x18002e79c  jmp     short loc_18002E7A3
0x18002e79e  mov     ebp, 0Ah
0x18002e7a3  lea     rdi, ds:0[rbp*8]
0x18002e7ab  call    cs:__imp_GetProcessHeap
0x18002e7b1  mov     r8, rdi; dwBytes
0x18002e7b4  xor     edx, edx; dwFlags
0x18002e7b6  mov     rcx, rax; hHeap
0x18002e7b9  call    cs:__imp_HeapAlloc
0x18002e7bf  mov     r15, rax
0x18002e7c2  test    rax, rax
0x18002e7c5  jz      short loc_18002E823
0x18002e7c7  cmp     qword ptr [rsi], 0
0x18002e7cb  jz      short loc_18002E81A
0x18002e7cd  xor     edi, edi
0x18002e7cf  cmp     [rsi+10h], rdi
0x18002e7d3  jbe     short loc_18002E803
0x18002e7d5  mov     rcx, [rsi]
0x18002e7d8  mov     rax, [rcx+rdi*8]
0x18002e7dc  mov     [r15+rdi*8], rax
0x18002e7e0  mov     qword ptr [rcx+rdi*8], 0
0x18002e7e8  mov     rax, [rsi]
0x18002e7eb  mov     rcx, [rax+rdi*8]; pv
0x18002e7ef  test    rcx, rcx
0x18002e7f2  jz      short loc_18002E7FA
0x18002e7f4  call    cs:__imp_CoTaskMemFree
0x18002e7fa  inc     rdi
0x18002e7fd  cmp     rdi, [rsi+10h]
0x18002e801  jb      short loc_18002E7D5
0x18002e803  mov     rdi, [rsi]
0x18002e806  call    cs:__imp_GetProcessHeap
0x18002e80c  mov     r8, rdi; lpMem
0x18002e80f  xor     edx, edx; dwFlags
0x18002e811  mov     rcx, rax; hHeap
0x18002e814  call    cs:__imp_HeapFree
0x18002e81a  mov     [rsi], r15
0x18002e81d  mov     [rsi+8], rbp
0x18002e821  mov     al, 1
0x18002e823  test    al, al
0x18002e825  jnz     short loc_18002E82E
0x18002e827  mov     rcx, [rsp+58h+arg_0]
0x18002e82c  jmp     short loc_18002E844
0x18002e82e  mov     rdx, [rsi+10h]
0x18002e832  mov     rcx, [rsi]
0x18002e835  mov     rax, [rsp+58h+arg_0]
0x18002e83a  mov     [rcx+rdx*8], rax
0x18002e83e  xor     ecx, ecx; pv
0x18002e840  inc     qword ptr [rsi+10h]
0x18002e844  test    rcx, rcx
0x18002e847  jz      short loc_18002E84F
0x18002e849  call    cs:__imp_CoTaskMemFree
0x18002e84f  test    rbx, rbx
0x18002e852  jnz     loc_18002E763
0x18002e858  add     rsp, 28h
0x18002e85c  pop     r15
0x18002e85e  pop     r14
0x18002e860  pop     rdi
0x18002e861  pop     rsi
0x18002e862  pop     rbp
0x18002e863  pop     rbx
0x18002e864  retn
```
