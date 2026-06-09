# GetAutoListInitFromFolderAndView

- ea: `0x18003e5d0`
- end: `0x18003e75c`
- name: `GetAutoListInitFromFolderAndView`
- size: `396`
- prototype: `__int64 __usercall@<rax>(struct IUnknown *@<rcx>, struct IFolderView2 *@<rdx>, struct AUTOLISTINIT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ef00`

## callees

- `0x180004a50`
- `0x180006900`
- `0x1800076dc`
- `0x180011eb8`
- `0x180011f3c`
- `0x180013638`
- `0x18001479c`
- `0x18003e0d8`
- `0x18003e5d0`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e6c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e707`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e711`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e6c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e707`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e711`

## pseudocode

```c
__int64 __fastcall GetAutoListInitFromFolderAndView(
        struct IUnknown *a1,
        struct IFolderView2 *a2,
        _OWORD *a3,
        __int64 a4,
        struct AUTOLISTINIT *a5)
{
  int AUTOLISTINITFromAutoListDescription; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  int v10; // eax
  int v11; // esi
  void *v13; // [rsp+20h] [rbp-48h] BYREF
  __int128 Source; // [rsp+28h] [rbp-40h] BYREF
  int v15; // [rsp+38h] [rbp-30h]

  memset_0(a5, 0, 0xB0u);
  v13 = 0;
  AUTOLISTINITFromAutoListDescription = IUnknown_QueryObject(
                                          a1,
                                          &GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82,
                                          &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                                          &v13);
  if ( AUTOLISTINITFromAutoListDescription >= 0 )
  {
    AUTOLISTINITFromAutoListDescription = GetAUTOLISTINITFromAutoListDescription(v13, 3, a5);
    if ( AUTOLISTINITFromAutoListDescription >= 0 )
    {
      *((_OWORD *)a5 + 1) = *a3;
      SafeRelease<IShellItemArray>((__int64 *)a5 + 15);
      AUTOLISTINITFromAutoListDescription = IUnknown_QueryObject(
                                              a1,
                                              &GUID_03fe6a93_5d4e_46a0_8d89_7c19165fa173,
                                              &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495,
                                              (void **)a5 + 15);
      if ( AUTOLISTINITFromAutoListDescription < 0 )
        goto LABEL_9;
      v15 = 0;
      lpVtbl = a1->lpVtbl;
      Source = 0;
      v10 = ((__int64 (__fastcall *)(struct IUnknown *, __int128 *))lpVtbl[8].AddRef)(a1, &Source);
      AUTOLISTINITFromAutoListDescription = v10;
      if ( v10 < 0 )
        goto LABEL_9;
      if ( v10 )
      {
        v11 = 0;
      }
      else
      {
        CoTaskMemFree(*((LPVOID *)a5 + 11));
        v11 = 1;
        *((_DWORD *)a5 + 21) = 1;
        AUTOLISTINITFromAutoListDescription = SHCoDupArray<_tagpropertykey>(&Source, 1u, (void **)a5 + 11);
        if ( AUTOLISTINITFromAutoListDescription < 0 )
        {
LABEL_9:
          ClearAutoListInit(a5);
          CoTaskMemFree(*((LPVOID *)a5 + 11));
          CoTaskMemFree(*((LPVOID *)a5 + 13));
          memset_0(a5, 0, 0xB0u);
          goto LABEL_10;
        }
      }
      AUTOLISTINITFromAutoListDescription = ApplyViewInfoToAUTOLISTINIT(a5, a2, v11);
      if ( AUTOLISTINITFromAutoListDescription < 0 )
        goto LABEL_9;
    }
LABEL_10:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)AUTOLISTINITFromAutoListDescription;
}

```

## disassembly

```asm
0x18003e5d0  mov     [rsp+arg_10], rbx
0x18003e5d5  mov     [rsp+arg_18], rbp
0x18003e5da  push    rsi
0x18003e5db  push    rdi
0x18003e5dc  push    r14
0x18003e5de  sub     rsp, 50h
0x18003e5e2  mov     rax, cs:__security_cookie
0x18003e5e9  xor     rax, rsp
0x18003e5ec  mov     [rsp+68h+var_28], rax
0x18003e5f1  mov     rdi, [rsp+68h+arg_20]
0x18003e5f9  mov     rbp, r8
0x18003e5fc  mov     r14, rdx
0x18003e5ff  mov     rsi, rcx
0x18003e602  mov     rcx, rdi; void *
0x18003e605  xor     edx, edx; Val
0x18003e607  mov     r8d, 0B0h; Size
0x18003e60d  call    memset_0
0x18003e612  lea     r9, [rsp+68h+var_48]; void **
0x18003e617  mov     [rsp+68h+var_48], 0
0x18003e620  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456; struct _GUID *
0x18003e627  mov     rcx, rsi; struct IUnknown *
0x18003e62a  lea     rdx, _GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82; struct _GUID *
0x18003e631  call    ?IUnknown_QueryObject@@YAJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z; IUnknown_QueryObject(IUnknown *,_GUID const &,_GUID const &,void * *)
0x18003e636  mov     ebx, eax
0x18003e638  test    eax, eax
0x18003e63a  js      loc_18003E738
0x18003e640  mov     rcx, [rsp+68h+var_48]
0x18003e645  mov     r8, rdi
0x18003e648  mov     edx, 3
0x18003e64d  call    ?GetAUTOLISTINITFromAutoListDescription@@YAJPEAUIAutoListDescription@@W4AUTOLISTINIT_FLAGS@@PEAUAUTOLISTINIT@@@Z; GetAUTOLISTINITFromAutoListDescription(IAutoListDescription *,AUTOLISTINIT_FLAGS,AUTOLISTINIT *)
0x18003e652  mov     ebx, eax
0x18003e654  test    eax, eax
0x18003e656  js      loc_18003E727
0x18003e65c  movaps  xmm0, xmmword ptr [rbp+0]
0x18003e660  lea     rcx, [rdi+78h]
0x18003e664  movdqu  xmmword ptr [rdi+10h], xmm0
0x18003e669  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x18003e66e  lea     r9, [rdi+78h]; void **
0x18003e672  mov     rcx, rsi; struct IUnknown *
0x18003e675  lea     r8, _GUID_d18f09e2_81c2_4217_a295_43b66fa4e495; struct _GUID *
0x18003e67c  lea     rdx, _GUID_03fe6a93_5d4e_46a0_8d89_7c19165fa173; struct _GUID *
0x18003e683  call    ?IUnknown_QueryObject@@YAJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z; IUnknown_QueryObject(IUnknown *,_GUID const &,_GUID const &,void * *)
0x18003e688  mov     ebx, eax
0x18003e68a  test    eax, eax
0x18003e68c  js      short loc_18003E6FB
0x18003e68e  xor     eax, eax
0x18003e690  lea     rdx, [rsp+68h+Source]
0x18003e695  mov     [rsp+68h+var_30], eax
0x18003e699  xorps   xmm0, xmm0
0x18003e69c  mov     rax, [rsi]
0x18003e69f  mov     rcx, rsi
0x18003e6a2  movups  [rsp+68h+Source], xmm0
0x18003e6a7  mov     rax, [rax+0C8h]
0x18003e6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6b3  mov     ebx, eax
0x18003e6b5  test    eax, eax
0x18003e6b7  js      short loc_18003E6FB
0x18003e6b9  jz      short loc_18003E6BF
0x18003e6bb  xor     esi, esi
0x18003e6bd  jmp     short loc_18003E6E7
0x18003e6bf  mov     rcx, [rdi+58h]; pv
0x18003e6c3  call    cs:__imp_CoTaskMemFree
0x18003e6c9  mov     esi, 1
0x18003e6ce  lea     r8, [rdi+58h]; void **
0x18003e6d2  mov     edx, esi; unsigned __int64
0x18003e6d4  mov     [rdi+54h], esi
0x18003e6d7  lea     rcx, [rsp+68h+Source]; Source
0x18003e6dc  call    ??$SHCoDupArray@U_tagpropertykey@@@@YAJPEBU_tagpropertykey@@_KPEAPEAU0@@Z; SHCoDupArray<_tagpropertykey>(_tagpropertykey const *,unsigned __int64,_tagpropertykey * *)
0x18003e6e1  mov     ebx, eax
0x18003e6e3  test    eax, eax
0x18003e6e5  js      short loc_18003E6FB
0x18003e6e7  mov     r8d, esi; int
0x18003e6ea  mov     rdx, r14; struct IFolderView2 *
0x18003e6ed  mov     rcx, rdi; struct AUTOLISTINIT *
0x18003e6f0  call    ?ApplyViewInfoToAUTOLISTINIT@@YAJPEAUAUTOLISTINIT@@PEAUIFolderView2@@H@Z; ApplyViewInfoToAUTOLISTINIT(AUTOLISTINIT *,IFolderView2 *,int)
0x18003e6f5  mov     ebx, eax
0x18003e6f7  test    eax, eax
0x18003e6f9  jns     short loc_18003E727
0x18003e6fb  mov     rcx, rdi; struct AUTOLISTINIT *
0x18003e6fe  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x18003e703  mov     rcx, [rdi+58h]; pv
0x18003e707  call    cs:__imp_CoTaskMemFree
0x18003e70d  mov     rcx, [rdi+68h]; pv
0x18003e711  call    cs:__imp_CoTaskMemFree
0x18003e717  xor     edx, edx; Val
0x18003e719  mov     r8d, 0B0h; Size
0x18003e71f  mov     rcx, rdi; void *
0x18003e722  call    memset_0
0x18003e727  mov     rcx, [rsp+68h+var_48]
0x18003e72c  mov     rax, [rcx]
0x18003e72f  mov     rax, [rax+10h]
0x18003e733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e738  mov     eax, ebx
0x18003e73a  mov     rcx, [rsp+68h+var_28]
0x18003e73f  xor     rcx, rsp; StackCookie
0x18003e742  call    __security_check_cookie
0x18003e747  lea     r11, [rsp+68h+var_18]
0x18003e74c  mov     rbx, [r11+30h]
0x18003e750  mov     rbp, [r11+38h]
0x18003e754  mov     rsp, r11
0x18003e757  pop     r14
0x18003e759  pop     rdi
0x18003e75a  pop     rsi
0x18003e75b  retn
```
