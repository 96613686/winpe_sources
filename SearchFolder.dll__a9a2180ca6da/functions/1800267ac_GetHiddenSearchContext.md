# GetHiddenSearchContext

- ea: `0x1800267ac`
- end: `0x1800269b9`
- name: `GetHiddenSearchContext`
- size: `525`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025da0`

## callees

- `0x18000bb60`
- `0x1800113b4`
- `0x180026100`
- `0x1800267ac`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18002693d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180026950`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180026963`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18002693d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180026950`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180026963`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180026855`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180026855`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180026840`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180026840`
- `SHELL32!SHCreateItemFromIDList` at `0x18002681e`
- `SHELL32!SHCreateItemFromIDList` at `0x18002681e`
- `SHELL32!__imp_ILFree` at `0x18002682a`
- `SHELL32!__imp_ILFree` at `0x18002682a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002687c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002690a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002687c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002690a`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x1800268bb`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x1800268bb`

## pseudocode

```c
__int64 __fastcall GetHiddenSearchContext(__int64 a1, IUnknown **a2, IUnknown **a3, IUnknown **a4)
{
  HRESULT Instance; // ebx
  unsigned __int16 *v8; // rax
  const BYTE *v9; // rcx
  IStream *v10; // rax
  struct IStream *v11; // rdi
  IUnknown *punk; // [rsp+30h] [rbp-20h] BYREF
  IUnknown *v14; // [rsp+38h] [rbp-18h] BYREF
  IUnknown *ppv; // [rsp+40h] [rbp-10h] BYREF
  LPCITEMIDLIST pidl; // [rsp+98h] [rbp+48h] BYREF
  int v17; // [rsp+A0h] [rbp+50h] BYREF
  int v18; // [rsp+A8h] [rbp+58h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  Instance = 1;
  v8 = (unsigned __int16 *)ILFindHiddenIDOn(a1, 3203334167LL);
  if ( v8 )
  {
    v9 = (const BYTE *)(v8 + 4);
    if ( v8[1] )
    {
      Instance = -2147024882;
      v10 = SHCreateMemStream(v9, (unsigned int)*v8 - 8);
      v11 = v10;
      if ( v10 )
      {
        IStream_Reset(v10);
        ppv = 0;
        Instance = CoCreateInstance(&CLSID_ShellItem, 0, 1u, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (LPVOID *)&ppv);
        if ( Instance >= 0 )
        {
          v18 = 0;
          Instance = LoadFromStreamNull(v11, ppv, &v18);
          if ( Instance >= 0 )
          {
            v14 = 0;
            Instance = SHCreateScope(0, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, &v14);
            if ( Instance >= 0 )
            {
              v17 = 0;
              Instance = LoadFromStreamNull(v11, v14, &v17);
              if ( Instance >= 0 )
              {
                punk = 0;
                Instance = CoCreateInstance(
                             &CLSID_ShellItemArray,
                             0,
                             1u,
                             &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                             (LPVOID *)&punk);
                if ( Instance >= 0 )
                {
                  LODWORD(pidl) = 0;
                  Instance = LoadFromStreamNull(v11, punk, (int *)&pidl);
                  if ( Instance >= 0 )
                  {
                    if ( (_DWORD)pidl )
                      IUnknown_Set(a4, punk);
                    if ( v17 )
                      IUnknown_Set(a3, v14);
                    if ( v18 )
                      IUnknown_Set(a2, ppv);
                  }
                  ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
                }
              }
              ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
            }
          }
          ((void (__fastcall *)(IUnknown *))ppv->lpVtbl->Release)(ppv);
        }
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
    else
    {
      *a2 = 0;
      pidl = 0;
      Instance = SHILClone((const struct _ITEMIDLIST_RELATIVE *)v9, (struct _ITEMIDLIST_RELATIVE **)&pidl);
      if ( Instance >= 0 )
      {
        Instance = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)a2);
        ILFree((LPITEMIDLIST)pidl);
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800267ac  push    rbp
0x1800267ae  push    rbx
0x1800267af  push    rsi
0x1800267b0  push    rdi
0x1800267b1  push    r12
0x1800267b3  push    r14
0x1800267b5  push    r15
0x1800267b7  mov     rbp, rsp
0x1800267ba  sub     rsp, 50h
0x1800267be  xor     r12d, r12d
0x1800267c1  mov     rsi, rdx
0x1800267c4  mov     [rdx], r12
0x1800267c7  mov     r14, r9
0x1800267ca  mov     [r8], r12
0x1800267cd  mov     edx, 0BEEF0017h
0x1800267d2  mov     r15, r8
0x1800267d5  mov     [r9], r12
0x1800267d8  lea     ebx, [r12+1]
0x1800267dd  call    ?ILFindHiddenIDOn@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@W4IDLHID@@H@Z; ILFindHiddenIDOn(_ITEMIDLIST_RELATIVE const *,IDLHID,int)
0x1800267e2  test    rax, rax
0x1800267e5  jz      loc_1800269A8
0x1800267eb  lea     rcx, [rax+8]; struct _ITEMIDLIST_RELATIVE *
0x1800267ef  cmp     [rax+2], r12w
0x1800267f4  jnz     short loc_180026835
0x1800267f6  lea     rdx, [rbp+pidl]; struct _ITEMIDLIST_RELATIVE **
0x1800267fa  mov     [rsi], r12
0x1800267fd  mov     [rbp+pidl], r12
0x180026801  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x180026806  mov     ebx, eax
0x180026808  test    eax, eax
0x18002680a  js      loc_1800269A8
0x180026810  mov     rcx, [rbp+pidl]; pidl
0x180026814  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18002681b  mov     r8, rsi; ppv
0x18002681e  call    cs:__imp_SHCreateItemFromIDList
0x180026824  mov     rcx, [rbp+pidl]; pidl
0x180026828  mov     ebx, eax
0x18002682a  call    cs:__imp_ILFree
0x180026830  jmp     loc_1800269A8
0x180026835  movzx   edx, word ptr [rax]
0x180026838  mov     ebx, 8007000Eh
0x18002683d  sub     edx, 8; cbInit
0x180026840  call    cs:__imp_SHCreateMemStream
0x180026846  mov     rdi, rax
0x180026849  test    rax, rax
0x18002684c  jz      loc_1800269A8
0x180026852  mov     rcx, rax; pstm
0x180026855  call    cs:__imp_IStream_Reset
0x18002685b  xor     edx, edx; pUnkOuter
0x18002685d  mov     [rbp+var_10], r12
0x180026861  lea     rax, [rbp+var_10]
0x180026865  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18002686c  mov     [rsp+50h+ppv], rax; ppv
0x180026871  lea     rcx, CLSID_ShellItem; rclsid
0x180026878  lea     r8d, [rdx+1]; dwClsContext
0x18002687c  call    cs:__imp_CoCreateInstance
0x180026882  mov     ebx, eax
0x180026884  test    eax, eax
0x180026886  js      loc_180026999
0x18002688c  mov     rdx, [rbp+var_10]; struct IUnknown *
0x180026890  lea     r8, [rbp+arg_18]; int *
0x180026894  mov     rcx, rdi; struct IStream *
0x180026897  mov     [rbp+arg_18], r12d
0x18002689b  call    ?LoadFromStreamNull@@YAJPEAUIStream@@PEAUIUnknown@@PEAH@Z; LoadFromStreamNull(IStream *,IUnknown *,int *)
0x1800268a0  mov     ebx, eax
0x1800268a2  test    eax, eax
0x1800268a4  js      loc_180026989
0x1800268aa  lea     r8, [rbp+var_18]
0x1800268ae  mov     [rbp+var_18], r12
0x1800268b2  lea     rdx, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x1800268b9  xor     ecx, ecx
0x1800268bb  call    cs:__imp_SHCreateScope
0x1800268c1  mov     ebx, eax
0x1800268c3  test    eax, eax
0x1800268c5  js      loc_180026989
0x1800268cb  mov     rdx, [rbp+var_18]; struct IUnknown *
0x1800268cf  lea     r8, [rbp+arg_10]; int *
0x1800268d3  mov     rcx, rdi; struct IStream *
0x1800268d6  mov     [rbp+arg_10], r12d
0x1800268da  call    ?LoadFromStreamNull@@YAJPEAUIStream@@PEAUIUnknown@@PEAH@Z; LoadFromStreamNull(IStream *,IUnknown *,int *)
0x1800268df  mov     ebx, eax
0x1800268e1  test    eax, eax
0x1800268e3  js      loc_180026979
0x1800268e9  xor     edx, edx; pUnkOuter
0x1800268eb  mov     [rbp+punk], r12
0x1800268ef  lea     rax, [rbp+punk]
0x1800268f3  lea     r9, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x1800268fa  mov     [rsp+50h+ppv], rax; ppv
0x1800268ff  lea     rcx, CLSID_ShellItemArray; rclsid
0x180026906  lea     r8d, [rdx+1]; dwClsContext
0x18002690a  call    cs:__imp_CoCreateInstance
0x180026910  mov     ebx, eax
0x180026912  test    eax, eax
0x180026914  js      short loc_180026979
0x180026916  mov     rdx, [rbp+punk]; struct IUnknown *
0x18002691a  lea     r8, [rbp+pidl]; int *
0x18002691e  mov     rcx, rdi; struct IStream *
0x180026921  mov     dword ptr [rbp+pidl], r12d
0x180026925  call    ?LoadFromStreamNull@@YAJPEAUIStream@@PEAUIUnknown@@PEAH@Z; LoadFromStreamNull(IStream *,IUnknown *,int *)
0x18002692a  mov     ebx, eax
0x18002692c  test    eax, eax
0x18002692e  js      short loc_180026969
0x180026930  cmp     dword ptr [rbp+pidl], r12d
0x180026934  jz      short loc_180026943
0x180026936  mov     rdx, [rbp+punk]; punk
0x18002693a  mov     rcx, r14; ppunk
0x18002693d  call    cs:__imp_IUnknown_Set
0x180026943  cmp     [rbp+arg_10], r12d
0x180026947  jz      short loc_180026956
0x180026949  mov     rdx, [rbp+var_18]; punk
0x18002694d  mov     rcx, r15; ppunk
0x180026950  call    cs:__imp_IUnknown_Set
0x180026956  cmp     [rbp+arg_18], r12d
0x18002695a  jz      short loc_180026969
0x18002695c  mov     rdx, [rbp+var_10]; punk
0x180026960  mov     rcx, rsi; ppunk
0x180026963  call    cs:__imp_IUnknown_Set
0x180026969  mov     rcx, [rbp+punk]
0x18002696d  mov     rax, [rcx]
0x180026970  mov     rax, [rax+10h]
0x180026974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026979  mov     rcx, [rbp+var_18]
0x18002697d  mov     rax, [rcx]
0x180026980  mov     rax, [rax+10h]
0x180026984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026989  mov     rcx, [rbp+var_10]
0x18002698d  mov     rax, [rcx]
0x180026990  mov     rax, [rax+10h]
0x180026994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026999  mov     rax, [rdi]
0x18002699c  mov     rcx, rdi
0x18002699f  mov     rax, [rax+10h]
0x1800269a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269a8  mov     eax, ebx
0x1800269aa  add     rsp, 50h
0x1800269ae  pop     r15
0x1800269b0  pop     r14
0x1800269b2  pop     r12
0x1800269b4  pop     rdi
0x1800269b5  pop     rsi
0x1800269b6  pop     rbx
0x1800269b7  pop     rbp
0x1800269b8  retn
```
