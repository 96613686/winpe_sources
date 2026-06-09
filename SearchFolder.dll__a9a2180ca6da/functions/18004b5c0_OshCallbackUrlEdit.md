# OshCallbackUrlEdit

- ea: `0x18004b5c0`
- end: `0x18004b7c8`
- name: `OshCallbackUrlEdit`
- size: `520`
- prototype: `__int64 __usercall@<rax>(IUri *pBaseUri@<rcx>, __int64, unsigned __int16 *, int, __int64, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004740`
- `0x180004e70`
- `0x180024c50`
- `0x18004b5c0`
- `0x18004b854`
- `0x18004b890`
- `0x18004c2a0`
- `0x180051010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004b786`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b786`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x18004b658`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x18004b658`
- `urlmon!CoInternetCombineIUri` at `0x18004b6b3`
- `urlmon!CoInternetCombineIUri` at `0x18004b6b3`
- `iertutil!__imp_OshPvAlloc` at `0x18004b73e`
- `iertutil!__imp_OshPvAlloc` at `0x18004b73e`
- `iertutil!__imp_OshFreePv` at `0x18004b77c`
- `iertutil!__imp_OshFreePv` at `0x18004b77c`

## pseudocode

```c
_BOOL8 __fastcall OshCallbackUrlEdit(
        IUri *pBaseUri,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        _DWORD *a5,
        unsigned __int16 *a6,
        int a7,
        unsigned __int16 **a8,
        int *a9)
{
  HRESULT v9; // ebx
  unsigned __int64 v11; // rsi
  unsigned __int16 *v12; // rax
  WCHAR *v13; // r14
  int *v14; // rdi
  unsigned __int16 *v15; // rax
  unsigned __int16 **v16; // rsi
  IUri *ppCombinedUri; // [rsp+30h] [rbp-28h] BYREF
  IUri *ppURI; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int64 v20[3]; // [rsp+40h] [rbp-18h] BYREF
  BSTR bstrString; // [rsp+A8h] [rbp+50h] BYREF

  v9 = 0;
  if ( !*a4 )
  {
    if ( pBaseUri )
    {
      v11 = a7;
      if ( a7 >= 0 )
      {
        v9 = -2147024882;
        v12 = (unsigned __int16 *)operator new(saturated_mul(a7 + 1, 2u));
        v13 = v12;
        if ( v12 )
        {
          v9 = StringCchCopyNW(v12, (int)v11 + 1, a6, v11);
          if ( v9 < 0 )
            goto LABEL_23;
          ppURI = 0;
          v9 = CreateUri(v13, 0x3002B81u, 0, &ppURI);
          if ( v9 < 0 )
            goto LABEL_23;
          LODWORD(bstrString) = 0;
          v9 = IsRelativeIUri(ppURI, &bstrString);
          if ( v9 >= 0 && (_DWORD)bstrString )
          {
            ppCombinedUri = 0;
            if ( (int)v11 <= 0 )
            {
              ppCombinedUri = pBaseUri;
              ((void (__fastcall *)(IUri *))pBaseUri->lpVtbl->AddRef)(pBaseUri);
            }
            else
            {
              v9 = CoInternetCombineIUri(pBaseUri, ppURI, 0, &ppCombinedUri, 0);
              if ( v9 )
                goto LABEL_22;
            }
            bstrString = 0;
            v9 = ((__int64 (__fastcall *)(IUri *, BSTR *))ppCombinedUri->lpVtbl->GetAbsoluteUri)(
                   ppCombinedUri,
                   &bstrString);
            if ( v9 >= 0 )
            {
              v20[0] = 0;
              v9 = StringCchLengthW(bstrString, 0x824u, v20);
              if ( v9 >= 0 )
              {
                v14 = a9;
                v9 = UIntPtrToInt(v20[0], a9);
                if ( v9 >= 0 )
                {
                  v9 = -2147024882;
                  v15 = (unsigned __int16 *)OshPvAlloc((unsigned int)(2 * *v14 + 2));
                  v16 = a8;
                  *a8 = v15;
                  if ( v15 )
                  {
                    v9 = StringCchCopyNW(v15, *v14 + 1, bstrString, *v14);
                    if ( v9 < 0 )
                      OshFreePv(*v16);
                    else
                      *a5 = 1;
                  }
                }
              }
              SysFreeString(bstrString);
            }
            ((void (__fastcall *)(IUri *))ppCombinedUri->lpVtbl->Release)(ppCombinedUri);
          }
LABEL_22:
          ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
LABEL_23:
          CZeroInitNew::operator delete(v13);
        }
      }
    }
  }
  return v9 >= 0;
}

```

## disassembly

```asm
0x18004b5c0  push    rbp
0x18004b5c2  push    rbx
0x18004b5c3  push    rsi
0x18004b5c4  push    rdi
0x18004b5c5  push    r14
0x18004b5c7  push    r15
0x18004b5c9  mov     rbp, rsp
0x18004b5cc  sub     rsp, 58h
0x18004b5d0  xor     ebx, ebx
0x18004b5d2  mov     rdi, rcx
0x18004b5d5  cmp     [r9], ebx
0x18004b5d8  jnz     loc_18004B7B4
0x18004b5de  test    rcx, rcx
0x18004b5e1  jz      loc_18004B7B4
0x18004b5e7  movsxd  rsi, [rbp+arg_30]
0x18004b5eb  test    esi, esi
0x18004b5ed  js      loc_18004B7B4
0x18004b5f3  lea     eax, [rsi+1]
0x18004b5f6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004b5fd  movsxd  r15, eax
0x18004b600  mov     ebx, 8007000Eh
0x18004b605  mov     eax, 2
0x18004b60a  mul     r15
0x18004b60d  cmovb   rax, rcx
0x18004b611  mov     rcx, rax; unsigned __int64
0x18004b614  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b619  mov     r14, rax
0x18004b61c  test    rax, rax
0x18004b61f  jz      loc_18004B7B4
0x18004b625  mov     r8, [rbp+arg_28]; unsigned __int16 *
0x18004b629  mov     r9, rsi; unsigned __int64
0x18004b62c  mov     rdx, r15; unsigned __int64
0x18004b62f  mov     rcx, rax; unsigned __int16 *
0x18004b632  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18004b637  mov     ebx, eax
0x18004b639  test    eax, eax
0x18004b63b  js      loc_18004B7AC
0x18004b641  lea     r9, [rbp+ppURI]; ppURI
0x18004b645  mov     [rbp+ppURI], 0
0x18004b64d  xor     r8d, r8d; dwReserved
0x18004b650  mov     edx, 3002B81h; dwFlags
0x18004b655  mov     rcx, r14; pwzURI
0x18004b658  call    cs:__imp_CreateUri
0x18004b65e  mov     ebx, eax
0x18004b660  test    eax, eax
0x18004b662  js      loc_18004B7AC
0x18004b668  mov     rcx, [rbp+ppURI]
0x18004b66c  lea     rdx, [rbp+bstrString]
0x18004b670  mov     dword ptr [rbp+bstrString], 0
0x18004b677  call    _IsRelativeIUri
0x18004b67c  mov     ebx, eax
0x18004b67e  test    eax, eax
0x18004b680  js      loc_18004B79C
0x18004b686  cmp     dword ptr [rbp+bstrString], 0
0x18004b68a  jz      loc_18004B79C
0x18004b690  mov     [rbp+ppCombinedUri], 0
0x18004b698  mov     rcx, rdi; pBaseUri
0x18004b69b  test    esi, esi
0x18004b69d  jle     short loc_18004B6C4
0x18004b69f  mov     rdx, [rbp+ppURI]; pRelativeUri
0x18004b6a3  lea     r9, [rbp+ppCombinedUri]; ppCombinedUri
0x18004b6a7  xor     r8d, r8d; dwCombineFlags
0x18004b6aa  mov     [rsp+58h+dwReserved], 0; dwReserved
0x18004b6b3  call    cs:__imp_CoInternetCombineIUri
0x18004b6b9  mov     ebx, eax
0x18004b6bb  test    eax, eax
0x18004b6bd  jz      short loc_18004B6D4
0x18004b6bf  jmp     loc_18004B79C
0x18004b6c4  mov     [rbp+ppCombinedUri], rdi
0x18004b6c8  mov     rax, [rdi]
0x18004b6cb  mov     rax, [rax+8]
0x18004b6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b6d4  mov     rcx, [rbp+ppCombinedUri]
0x18004b6d8  lea     rdx, [rbp+bstrString]
0x18004b6dc  mov     [rbp+bstrString], 0
0x18004b6e4  mov     rax, [rcx]
0x18004b6e7  mov     rax, [rax+38h]
0x18004b6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b6f0  mov     ebx, eax
0x18004b6f2  test    eax, eax
0x18004b6f4  js      loc_18004B78C
0x18004b6fa  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x18004b6fe  lea     r8, [rbp+var_18]; unsigned __int64 *
0x18004b702  mov     edx, 824h; unsigned __int64
0x18004b707  mov     [rbp+var_18], 0
0x18004b70f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004b714  mov     ebx, eax
0x18004b716  test    eax, eax
0x18004b718  js      short loc_18004B782
0x18004b71a  mov     rdi, [rbp+arg_40]
0x18004b71e  mov     rcx, [rbp+var_18]; unsigned __int64
0x18004b722  mov     rdx, rdi; int *
0x18004b725  call    ?UIntPtrToInt@@YAJ_KPEAH@Z; UIntPtrToInt(unsigned __int64,int *)
0x18004b72a  mov     ebx, eax
0x18004b72c  test    eax, eax
0x18004b72e  js      short loc_18004B782
0x18004b730  mov     ecx, [rdi]
0x18004b732  mov     ebx, 8007000Eh
0x18004b737  lea     ecx, ds:2[rcx*2]
0x18004b73e  call    cs:__imp_OshPvAlloc
0x18004b744  mov     rsi, [rbp+arg_38]
0x18004b748  mov     [rsi], rax
0x18004b74b  test    rax, rax
0x18004b74e  jz      short loc_18004B782
0x18004b750  movsxd  rcx, dword ptr [rdi]
0x18004b753  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x18004b757  mov     r9, rcx; unsigned __int64
0x18004b75a  inc     ecx
0x18004b75c  movsxd  rdx, ecx; unsigned __int64
0x18004b75f  mov     rcx, rax; unsigned __int16 *
0x18004b762  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18004b767  mov     ebx, eax
0x18004b769  test    eax, eax
0x18004b76b  js      short loc_18004B779
0x18004b76d  mov     rax, [rbp+arg_20]
0x18004b771  mov     dword ptr [rax], 1
0x18004b777  jmp     short loc_18004B782
0x18004b779  mov     rcx, [rsi]
0x18004b77c  call    cs:__imp_OshFreePv
0x18004b782  mov     rcx, [rbp+bstrString]; bstrString
0x18004b786  call    cs:__imp_SysFreeString
0x18004b78c  mov     rcx, [rbp+ppCombinedUri]
0x18004b790  mov     rax, [rcx]
0x18004b793  mov     rax, [rax+10h]
0x18004b797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b79c  mov     rcx, [rbp+ppURI]
0x18004b7a0  mov     rax, [rcx]
0x18004b7a3  mov     rax, [rax+10h]
0x18004b7a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b7ac  mov     rcx, r14; lpMem
0x18004b7af  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x18004b7b4  not     ebx
0x18004b7b6  shr     ebx, 1Fh
0x18004b7b9  mov     eax, ebx
0x18004b7bb  add     rsp, 58h
0x18004b7bf  pop     r15
0x18004b7c1  pop     r14
0x18004b7c3  pop     rdi
0x18004b7c4  pop     rsi
0x18004b7c5  pop     rbx
0x18004b7c6  pop     rbp
0x18004b7c7  retn
```
