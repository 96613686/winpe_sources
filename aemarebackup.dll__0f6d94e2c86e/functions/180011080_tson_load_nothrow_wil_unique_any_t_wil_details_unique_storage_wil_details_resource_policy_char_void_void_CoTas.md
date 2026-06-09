# tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::input_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x180011080`
- end: `0x180011249`
- name: `??$load_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `457`
- prototype: `void __fastcall(tson::input_archive *this, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180028028`

## callees

- `0x18000f1d4`
- `0x180011080`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011117`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001118f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800111ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011117`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001118f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800111ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011125`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800111f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011125`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800111f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001119d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001119d`
- `ole32!CoTaskMemFree` at `0x180011105`
- `ole32!CoTaskMemFree` at `0x1800111d8`
- `ole32!CoTaskMemFree` at `0x18001122d`
- `ole32!CoTaskMemFree` at `0x180011105`
- `ole32!CoTaskMemFree` at `0x1800111d8`
- `ole32!CoTaskMemFree` at `0x18001122d`

## pseudocode

```c
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
0x180011080  push    rbx
0x180011082  push    rbp
0x180011083  push    rsi
0x180011084  push    rdi
0x180011085  push    r14
0x180011087  push    r15
0x180011089  sub     rsp, 28h
0x18001108d  xor     ebx, ebx
0x18001108f  mov     rsi, rdx
0x180011092  mov     r14, rcx
0x180011095  cmp     [rcx+19h], bl
0x180011098  jnz     short loc_1800110EB
0x18001109a  lea     rax, [rcx+20h]
0x18001109e  mov     rcx, [rax+68h]
0x1800110a2  test    rcx, rcx
0x1800110a5  jz      short loc_1800110B1
0x1800110a7  lea     rax, [rax+rcx*4]
0x1800110ab  add     rax, 0FFFFFFFFFFFFFFFCh
0x1800110af  jmp     short loc_1800110B4
0x1800110b1  mov     byte ptr [rax], 1
0x1800110b4  cmp     dword ptr [rax+4], 1
0x1800110b8  jz      short loc_1800110C8
0x1800110ba  cmp     [r14+8], ebx
0x1800110be  jl      short loc_1800110C8
0x1800110c0  mov     dword ptr [r14+8], 8007065Dh
0x1800110c8  mov     rax, [r14]
0x1800110cb  mov     rcx, [rax+8]
0x1800110cf  lea     rdx, [rcx+2]
0x1800110d3  cmp     rdx, [rax+10h]
0x1800110d7  ja      short loc_1800110E2
0x1800110d9  movzx   ecx, word ptr [rcx]
0x1800110dc  mov     [rax+8], rdx
0x1800110e0  jmp     short loc_1800110E8
0x1800110e2  xor     ecx, ecx
0x1800110e4  mov     byte ptr [rax+18h], 1
0x1800110e8  movzx   ebx, cx
0x1800110eb  cmp     qword ptr [rsi], 0
0x1800110ef  jz      short loc_180011132
0x1800110f1  xor     edi, edi
0x1800110f3  cmp     [rsi+10h], rdi
0x1800110f7  jbe     short loc_180011114
0x1800110f9  mov     rax, [rsi]
0x1800110fc  mov     rcx, [rax+rdi*8]; pv
0x180011100  test    rcx, rcx
0x180011103  jz      short loc_18001110B
0x180011105  call    cs:__imp_CoTaskMemFree
0x18001110b  inc     rdi
0x18001110e  cmp     rdi, [rsi+10h]
0x180011112  jb      short loc_1800110F9
0x180011114  mov     rdi, [rsi]
0x180011117  call    cs:__imp_GetProcessHeap
0x18001111d  mov     r8, rdi; lpMem
0x180011120  xor     edx, edx; dwFlags
0x180011122  mov     rcx, rax; hHeap
0x180011125  call    cs:__imp_HeapFree
0x18001112b  mov     qword ptr [rsi], 0
0x180011132  mov     qword ptr [rsi+8], 0
0x18001113a  mov     qword ptr [rsi+10h], 0
0x180011142  jmp     loc_180011233
0x180011147  lea     rdx, [rsp+58h+arg_0]
0x18001114c  mov     [rsp+58h+arg_0], 0
0x180011155  mov     rcx, r14; this
0x180011158  dec     rbx
0x18001115b  call    ??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)
0x180011160  mov     rax, [rsi+8]
0x180011164  cmp     [rsi+10h], rax
0x180011168  jb      loc_180011212
0x18001116e  test    rax, rax
0x180011171  jz      short loc_180011182
0x180011173  lea     rbp, [rax+rax]
0x180011177  cmp     rbp, rax
0x18001117a  jbe     loc_180011205
0x180011180  jmp     short loc_180011187
0x180011182  mov     ebp, 0Ah
0x180011187  lea     rdi, ds:0[rbp*8]
0x18001118f  call    cs:__imp_GetProcessHeap
0x180011195  mov     r8, rdi; dwBytes
0x180011198  xor     edx, edx; dwFlags
0x18001119a  mov     rcx, rax; hHeap
0x18001119d  call    cs:__imp_HeapAlloc
0x1800111a3  mov     r15, rax
0x1800111a6  test    rax, rax
0x1800111a9  jz      short loc_180011207
0x1800111ab  cmp     qword ptr [rsi], 0
0x1800111af  jz      short loc_1800111FE
0x1800111b1  xor     edi, edi
0x1800111b3  cmp     [rsi+10h], rdi
0x1800111b7  jbe     short loc_1800111E7
0x1800111b9  mov     rcx, [rsi]
0x1800111bc  mov     rax, [rcx+rdi*8]
0x1800111c0  mov     [r15+rdi*8], rax
0x1800111c4  mov     qword ptr [rcx+rdi*8], 0
0x1800111cc  mov     rax, [rsi]
0x1800111cf  mov     rcx, [rax+rdi*8]; pv
0x1800111d3  test    rcx, rcx
0x1800111d6  jz      short loc_1800111DE
0x1800111d8  call    cs:__imp_CoTaskMemFree
0x1800111de  inc     rdi
0x1800111e1  cmp     rdi, [rsi+10h]
0x1800111e5  jb      short loc_1800111B9
0x1800111e7  mov     rdi, [rsi]
0x1800111ea  call    cs:__imp_GetProcessHeap
0x1800111f0  mov     r8, rdi; lpMem
0x1800111f3  xor     edx, edx; dwFlags
0x1800111f5  mov     rcx, rax; hHeap
0x1800111f8  call    cs:__imp_HeapFree
0x1800111fe  mov     [rsi], r15
0x180011201  mov     [rsi+8], rbp
0x180011205  mov     al, 1
0x180011207  test    al, al
0x180011209  jnz     short loc_180011212
0x18001120b  mov     rcx, [rsp+58h+arg_0]
0x180011210  jmp     short loc_180011228
0x180011212  mov     rdx, [rsi+10h]
0x180011216  mov     rcx, [rsi]
0x180011219  mov     rax, [rsp+58h+arg_0]
0x18001121e  mov     [rcx+rdx*8], rax
0x180011222  xor     ecx, ecx; pv
0x180011224  inc     qword ptr [rsi+10h]
0x180011228  test    rcx, rcx
0x18001122b  jz      short loc_180011233
0x18001122d  call    cs:__imp_CoTaskMemFree
0x180011233  test    rbx, rbx
0x180011236  jnz     loc_180011147
0x18001123c  add     rsp, 28h
0x180011240  pop     r15
0x180011242  pop     r14
0x180011244  pop     rdi
0x180011245  pop     rsi
0x180011246  pop     rbp
0x180011247  pop     rbx
0x180011248  retn
```
