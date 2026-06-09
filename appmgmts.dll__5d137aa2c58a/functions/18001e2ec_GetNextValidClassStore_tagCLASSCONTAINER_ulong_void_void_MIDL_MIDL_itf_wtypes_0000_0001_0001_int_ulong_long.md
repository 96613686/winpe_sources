# GetNextValidClassStore(tagCLASSCONTAINER * *,ulong,void *,void *,__MIDL___MIDL_itf_wtypes_0000_0001_0001 *,int,ulong *,long *)

- ea: `0x18001e2ec`
- end: `0x18001e4a6`
- name: `?GetNextValidClassStore@@YAPEAUIClassAccess@@PEAPEAUtagCLASSCONTAINER@@KPEAX1PEAU__MIDL___MIDL_itf_wtypes_0000_0001_0001@@HPEAKPEAJ@Z`
- size: `442`
- prototype: `struct IClassAccess *__fastcall(struct tagCLASSCONTAINER **, unsigned int, void *, void *, struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *, int, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ddc0`
- `0x18001e100`

## callees

- `0x180013058`
- `0x18001b1a0`
- `0x18001c84c`
- `0x18001e2ec`
- `0x18002ad84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001e3c3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001e3c3`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001e381`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001e395`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001e3ac`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001e381`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001e395`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001e3ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e471`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e471`

## pseudocode

```c
struct IClassAccess *__fastcall GetNextValidClassStore(
        struct tagCLASSCONTAINER **a1,
        unsigned int a2,
        void *a3,
        void *a4,
        struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *a5,
        int a6,
        unsigned int *a7,
        unsigned int *a8)
{
  unsigned int *v8; // rdi
  HLOCAL v9; // rsi
  int *v11; // rbp
  int v12; // ebx
  __int64 v15; // rax
  const wchar_t ***v16; // r15
  wchar_t *v17; // rax
  wchar_t *v18; // rax
  wchar_t *v19; // rbx
  const unsigned __int16 *v20; // rbx
  struct CServerContext *v21; // rdx
  CAppContainerCF *v22; // rcx
  int ConnectedInstance; // eax
  HLOCAL hMem; // [rsp+40h] [rbp-58h] BYREF

  v8 = a8;
  v9 = 0;
  hMem = 0;
  v11 = 0;
  v12 = 0;
  *a8 = 0;
  if ( !a5 )
    goto LABEL_27;
  LOBYTE(v12) = a5->tyspec == 5;
  if ( a5->tyspec != 5 )
    goto LABEL_27;
  GuidToString(&a5->tagged_union.ByName.PolicyId, (unsigned __int16 **)&hMem);
  v9 = hMem;
  if ( !hMem )
    *v8 = -2147024882;
  if ( (*v8 & 0x80000000) == 0 )
  {
LABEL_27:
    v15 = *a7;
    v16 = (const wchar_t ***)&a1[v15];
    if ( (unsigned int)v15 < a2 )
    {
      if ( v12 )
      {
        while ( 1 )
        {
          v17 = wcschr(**v16, 0x2Cu);
          if ( v17 )
          {
            v18 = wcschr(v17 + 1, 0x2Cu);
            if ( v18 )
            {
              v19 = v18 + 4;
              if ( wcschr(v18, 0x7Bu) == v18 + 4 && !(unsigned int)_o__wcsnicmp(v19, v9, 38) )
                break;
            }
          }
          if ( ++*a7 >= a2 )
            goto LABEL_20;
          ++v16;
        }
      }
      if ( gDebug )
        _DebugMsg(2, 0xC90u, *a7, **v16);
      v20 = **v16;
      if ( !wcsncmp_0(v20, L"LDAP:", 5u) )
      {
        a8 = 0;
        ConnectedInstance = CAppContainerCF::CreateConnectedInstance(v22, v21, v20, a3, a4, a6, (void **)&a8);
        *v8 = ConnectedInstance;
        if ( ConnectedInstance >= 0 )
          v11 = (int *)a8;
      }
      else
      {
        *v8 = -2147221141;
      }
    }
  }
LABEL_20:
  if ( v9 )
    LocalFree(v9);
  if ( gDebug )
    _DebugMsg(2, 0xC91u, *v8);
  return (struct IClassAccess *)v11;
}

```

## disassembly

```asm
0x18001e2ec  mov     [rsp+arg_10], r8
0x18001e2f1  push    rbx
0x18001e2f2  push    rbp
0x18001e2f3  push    rsi
0x18001e2f4  push    rdi
0x18001e2f5  push    r12
0x18001e2f7  push    r13
0x18001e2f9  push    r14
0x18001e2fb  push    r15
0x18001e2fd  sub     rsp, 58h
0x18001e301  mov     rdi, [rsp+98h+arg_38]
0x18001e309  xor     esi, esi
0x18001e30b  mov     r15, rcx
0x18001e30e  mov     [rsp+98h+hMem], rsi
0x18001e313  mov     rcx, [rsp+98h+arg_20]
0x18001e31b  xor     ebp, ebp
0x18001e31d  xor     ebx, ebx
0x18001e31f  mov     r13, r9
0x18001e322  mov     [rdi], esi
0x18001e324  mov     r12d, edx
0x18001e327  test    rcx, rcx
0x18001e32a  jz      short loc_18001E35A
0x18001e32c  cmp     dword ptr [rcx], 5
0x18001e32f  setz    bl
0x18001e332  jnz     short loc_18001E35A
0x18001e334  add     rcx, 10h; struct _GUID *
0x18001e338  lea     rdx, [rsp+98h+hMem]; unsigned __int16 **
0x18001e33d  call    ?GuidToString@@YAXAEAU_GUID@@PEAPEAG@Z; GuidToString(_GUID &,ushort * *)
0x18001e342  mov     rsi, [rsp+98h+hMem]
0x18001e347  test    rsi, rsi
0x18001e34a  jnz     short loc_18001E352
0x18001e34c  mov     dword ptr [rdi], 8007000Eh
0x18001e352  cmp     [rdi], ebp
0x18001e354  jl      loc_18001E469
0x18001e35a  mov     r14, [rsp+98h+arg_30]
0x18001e362  mov     eax, [r14]
0x18001e365  lea     r15, [r15+rax*8]
0x18001e369  cmp     eax, r12d
0x18001e36c  jnb     loc_18001E469
0x18001e372  test    ebx, ebx
0x18001e374  jz      short loc_18001E3DF
0x18001e376  mov     rcx, [r15]
0x18001e379  mov     edx, 2Ch ; ','; Ch
0x18001e37e  mov     rcx, [rcx]; Str
0x18001e381  call    cs:__imp_wcschr
0x18001e387  test    rax, rax
0x18001e38a  jz      short loc_18001E3CD
0x18001e38c  mov     edx, 2Ch ; ','; Ch
0x18001e391  lea     rcx, [rax+2]; Str
0x18001e395  call    cs:__imp_wcschr
0x18001e39b  test    rax, rax
0x18001e39e  jz      short loc_18001E3CD
0x18001e3a0  mov     edx, 7Bh ; '{'; Ch
0x18001e3a5  lea     rbx, [rax+8]
0x18001e3a9  mov     rcx, rax; Str
0x18001e3ac  call    cs:__imp_wcschr
0x18001e3b2  cmp     rax, rbx
0x18001e3b5  jnz     short loc_18001E3CD
0x18001e3b7  mov     r8d, 26h ; '&'
0x18001e3bd  mov     rdx, rsi
0x18001e3c0  mov     rcx, rbx
0x18001e3c3  call    cs:__imp__o__wcsnicmp
0x18001e3c9  test    eax, eax
0x18001e3cb  jz      short loc_18001E3DF
0x18001e3cd  inc     dword ptr [r14]
0x18001e3d0  cmp     [r14], r12d
0x18001e3d3  jnb     loc_18001E469
0x18001e3d9  add     r15, 8
0x18001e3dd  jmp     short loc_18001E376
0x18001e3df  cmp     cs:?gDebug@@3KA, ebp; ulong gDebug
0x18001e3e5  jz      short loc_18001E3FF
0x18001e3e7  mov     r9, [r15]
0x18001e3ea  mov     edx, 0C90h; unsigned int
0x18001e3ef  mov     r8d, [r14]
0x18001e3f2  mov     ecx, 2; unsigned int
0x18001e3f7  mov     r9, [r9]
0x18001e3fa  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001e3ff  mov     rax, [r15]
0x18001e402  lea     rdx, aLdap_0; "LDAP:"
0x18001e409  mov     r8d, 5; MaxCount
0x18001e40f  mov     rbx, [rax]
0x18001e412  mov     rcx, rbx; String1
0x18001e415  call    wcsncmp_0
0x18001e41a  test    eax, eax
0x18001e41c  jnz     short loc_18001E463
0x18001e41e  mov     r9, [rsp+98h+arg_10]; void *
0x18001e426  lea     rax, [rsp+98h+arg_38]
0x18001e42e  mov     [rsp+98h+var_68], rax; void **
0x18001e433  mov     r8, rbx; unsigned __int16 *
0x18001e436  mov     eax, [rsp+98h+arg_28]
0x18001e43d  mov     [rsp+98h+var_70], eax; int
0x18001e441  mov     [rsp+98h+var_78], r13; void *
0x18001e446  mov     [rsp+98h+arg_38], rbp
0x18001e44e  call    ?CreateConnectedInstance@CAppContainerCF@@QEAAJPEAVCServerContext@@PEBGPEAX2HPEAPEAX@Z; CAppContainerCF::CreateConnectedInstance(CServerContext *,ushort const *,void *,void *,int,void * *)
0x18001e453  mov     [rdi], eax
0x18001e455  test    eax, eax
0x18001e457  js      short loc_18001E469
0x18001e459  mov     rbp, [rsp+98h+arg_38]
0x18001e461  jmp     short loc_18001E469
0x18001e463  mov     dword ptr [rdi], 8004016Bh
0x18001e469  test    rsi, rsi
0x18001e46c  jz      short loc_18001E477
0x18001e46e  mov     rcx, rsi; hMem
0x18001e471  call    cs:__imp_LocalFree
0x18001e477  cmp     cs:?gDebug@@3KA, 0; ulong gDebug
0x18001e47e  jz      short loc_18001E492
0x18001e480  mov     r8d, [rdi]
0x18001e483  mov     edx, 0C91h; unsigned int
0x18001e488  mov     ecx, 2; unsigned int
0x18001e48d  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001e492  mov     rax, rbp
0x18001e495  add     rsp, 58h
0x18001e499  pop     r15
0x18001e49b  pop     r14
0x18001e49d  pop     r13
0x18001e49f  pop     r12
0x18001e4a1  pop     rdi
0x18001e4a2  pop     rsi
0x18001e4a3  pop     rbp
0x18001e4a4  pop     rbx
0x18001e4a5  retn
```
