# tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::input_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x180058d58`
- end: `0x180058f21`
- name: `??$load_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `457`
- prototype: `void __fastcall(tson::input_archive *this, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18005e288`
- `0x1801ff140`

## callees

- `0x180058894`
- `0x180058d58`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180058def`
- `KERNEL32!GetProcessHeap` at `0x180058e67`
- `KERNEL32!GetProcessHeap` at `0x180058ec2`
- `KERNEL32!GetProcessHeap` at `0x180058def`
- `KERNEL32!GetProcessHeap` at `0x180058e67`
- `KERNEL32!GetProcessHeap` at `0x180058ec2`
- `KERNEL32!HeapAlloc` at `0x180058e75`
- `KERNEL32!HeapAlloc` at `0x180058e75`
- `KERNEL32!HeapFree` at `0x180058dfd`
- `KERNEL32!HeapFree` at `0x180058ed0`
- `KERNEL32!HeapFree` at `0x180058dfd`
- `KERNEL32!HeapFree` at `0x180058ed0`
- `OLE32!CoTaskMemFree` at `0x180058ddd`
- `OLE32!CoTaskMemFree` at `0x180058eb0`
- `OLE32!CoTaskMemFree` at `0x180058f05`
- `OLE32!CoTaskMemFree` at `0x180058ddd`
- `OLE32!CoTaskMemFree` at `0x180058eb0`
- `OLE32!CoTaskMemFree` at `0x180058f05`

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
0x180058d58  push    rbx
0x180058d5a  push    rbp
0x180058d5b  push    rsi
0x180058d5c  push    rdi
0x180058d5d  push    r14
0x180058d5f  push    r15
0x180058d61  sub     rsp, 28h
0x180058d65  xor     ebx, ebx
0x180058d67  mov     rsi, rdx
0x180058d6a  mov     r14, rcx
0x180058d6d  cmp     [rcx+19h], bl
0x180058d70  jnz     short loc_180058DC3
0x180058d72  lea     rax, [rcx+20h]
0x180058d76  mov     rcx, [rax+68h]
0x180058d7a  test    rcx, rcx
0x180058d7d  jz      short loc_180058D89
0x180058d7f  lea     rax, [rax+rcx*4]
0x180058d83  add     rax, 0FFFFFFFFFFFFFFFCh
0x180058d87  jmp     short loc_180058D8C
0x180058d89  mov     byte ptr [rax], 1
0x180058d8c  cmp     dword ptr [rax+4], 1
0x180058d90  jz      short loc_180058DA0
0x180058d92  cmp     [r14+8], ebx
0x180058d96  jl      short loc_180058DA0
0x180058d98  mov     dword ptr [r14+8], 8007065Dh
0x180058da0  mov     rax, [r14]
0x180058da3  mov     rcx, [rax+8]
0x180058da7  lea     rdx, [rcx+2]
0x180058dab  cmp     rdx, [rax+10h]
0x180058daf  ja      short loc_180058DBA
0x180058db1  movzx   ecx, word ptr [rcx]
0x180058db4  mov     [rax+8], rdx
0x180058db8  jmp     short loc_180058DC0
0x180058dba  xor     ecx, ecx
0x180058dbc  mov     byte ptr [rax+18h], 1
0x180058dc0  movzx   ebx, cx
0x180058dc3  cmp     qword ptr [rsi], 0
0x180058dc7  jz      short loc_180058E0A
0x180058dc9  xor     edi, edi
0x180058dcb  cmp     [rsi+10h], rdi
0x180058dcf  jbe     short loc_180058DEC
0x180058dd1  mov     rax, [rsi]
0x180058dd4  mov     rcx, [rax+rdi*8]; pv
0x180058dd8  test    rcx, rcx
0x180058ddb  jz      short loc_180058DE3
0x180058ddd  call    cs:__imp_CoTaskMemFree
0x180058de3  inc     rdi
0x180058de6  cmp     rdi, [rsi+10h]
0x180058dea  jb      short loc_180058DD1
0x180058dec  mov     rdi, [rsi]
0x180058def  call    cs:__imp_GetProcessHeap
0x180058df5  mov     r8, rdi; lpMem
0x180058df8  xor     edx, edx; dwFlags
0x180058dfa  mov     rcx, rax; hHeap
0x180058dfd  call    cs:__imp_HeapFree
0x180058e03  mov     qword ptr [rsi], 0
0x180058e0a  mov     qword ptr [rsi+8], 0
0x180058e12  mov     qword ptr [rsi+10h], 0
0x180058e1a  jmp     loc_180058F0B
0x180058e1f  lea     rdx, [rsp+58h+arg_0]
0x180058e24  mov     [rsp+58h+arg_0], 0
0x180058e2d  mov     rcx, r14; this
0x180058e30  dec     rbx
0x180058e33  call    ??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)
0x180058e38  mov     rax, [rsi+8]
0x180058e3c  cmp     [rsi+10h], rax
0x180058e40  jb      loc_180058EEA
0x180058e46  test    rax, rax
0x180058e49  jz      short loc_180058E5A
0x180058e4b  lea     rbp, [rax+rax]
0x180058e4f  cmp     rbp, rax
0x180058e52  jbe     loc_180058EDD
0x180058e58  jmp     short loc_180058E5F
0x180058e5a  mov     ebp, 0Ah
0x180058e5f  lea     rdi, ds:0[rbp*8]
0x180058e67  call    cs:__imp_GetProcessHeap
0x180058e6d  mov     r8, rdi; dwBytes
0x180058e70  xor     edx, edx; dwFlags
0x180058e72  mov     rcx, rax; hHeap
0x180058e75  call    cs:__imp_HeapAlloc
0x180058e7b  mov     r15, rax
0x180058e7e  test    rax, rax
0x180058e81  jz      short loc_180058EDF
0x180058e83  cmp     qword ptr [rsi], 0
0x180058e87  jz      short loc_180058ED6
0x180058e89  xor     edi, edi
0x180058e8b  cmp     [rsi+10h], rdi
0x180058e8f  jbe     short loc_180058EBF
0x180058e91  mov     rcx, [rsi]
0x180058e94  mov     rax, [rcx+rdi*8]
0x180058e98  mov     [r15+rdi*8], rax
0x180058e9c  mov     qword ptr [rcx+rdi*8], 0
0x180058ea4  mov     rax, [rsi]
0x180058ea7  mov     rcx, [rax+rdi*8]; pv
0x180058eab  test    rcx, rcx
0x180058eae  jz      short loc_180058EB6
0x180058eb0  call    cs:__imp_CoTaskMemFree
0x180058eb6  inc     rdi
0x180058eb9  cmp     rdi, [rsi+10h]
0x180058ebd  jb      short loc_180058E91
0x180058ebf  mov     rdi, [rsi]
0x180058ec2  call    cs:__imp_GetProcessHeap
0x180058ec8  mov     r8, rdi; lpMem
0x180058ecb  xor     edx, edx; dwFlags
0x180058ecd  mov     rcx, rax; hHeap
0x180058ed0  call    cs:__imp_HeapFree
0x180058ed6  mov     [rsi], r15
0x180058ed9  mov     [rsi+8], rbp
0x180058edd  mov     al, 1
0x180058edf  test    al, al
0x180058ee1  jnz     short loc_180058EEA
0x180058ee3  mov     rcx, [rsp+58h+arg_0]
0x180058ee8  jmp     short loc_180058F00
0x180058eea  mov     rdx, [rsi+10h]
0x180058eee  mov     rcx, [rsi]
0x180058ef1  mov     rax, [rsp+58h+arg_0]
0x180058ef6  mov     [rcx+rdx*8], rax
0x180058efa  xor     ecx, ecx; pv
0x180058efc  inc     qword ptr [rsi+10h]
0x180058f00  test    rcx, rcx
0x180058f03  jz      short loc_180058F0B
0x180058f05  call    cs:__imp_CoTaskMemFree
0x180058f0b  test    rbx, rbx
0x180058f0e  jnz     loc_180058E1F
0x180058f14  add     rsp, 28h
0x180058f18  pop     r15
0x180058f1a  pop     r14
0x180058f1c  pop     rdi
0x180058f1d  pop     rsi
0x180058f1e  pop     rbp
0x180058f1f  pop     rbx
0x180058f20  retn
```
