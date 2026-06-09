# CActionsContextMenuProvider::_DoesAppImplementSearchContract(void)

- ea: `0x18005ef4c`
- end: `0x18005f114`
- name: `?_DoesAppImplementSearchContract@CActionsContextMenuProvider@@AEAA_NXZ`
- size: `456`
- prototype: `bool __fastcall(CActionsContextMenuProvider *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005ee24`

## callees

- `0x180004c98`
- `0x18001e260`
- `0x18005ef4c`
- `0x1800637e4`
- `0x18006483c`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005f0c4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005f0c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall CActionsContextMenuProvider::_DoesAppImplementSearchContract(CActionsContextMenuProvider *this)
{
  bool v2; // si
  const unsigned __int16 *v3; // rdx
  const unsigned __int16 *v4; // rcx
  const struct _GUID *v5; // r8
  unsigned int v6; // r15d
  void *v7; // rdi
  int (__fastcall *v8)(void *, _QWORD, GUID *, struct IExtensionListItem **); // rbx
  __int64 v9; // rdx
  LPCWCH v10; // rcx
  int v11; // r9d
  const WCHAR *v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rax
  const WCHAR *v15; // rcx
  LPCWCH lpString2; // [rsp+30h] [rbp-20h] BYREF
  __int64 v18; // [rsp+38h] [rbp-18h]
  __int64 v19; // [rsp+40h] [rbp-10h]
  unsigned int v20; // [rsp+90h] [rbp+40h] BYREF
  void *v21; // [rsp+98h] [rbp+48h] BYREF
  struct IExtensionListItem *v22; // [rsp+A0h] [rbp+50h] BYREF

  v2 = 0;
  if ( *((_QWORD *)this + 20) )
  {
    v21 = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v21);
    if ( (int)CExtensionList::CreateInstance(v4, v3, v5, &v21) >= 0 )
    {
      v20 = 0;
      if ( (*(int (__fastcall **)(void *, unsigned int *))(*(_QWORD *)v21 + 24LL))(v21, &v20) >= 0 )
      {
        v6 = 0;
        while ( 1 )
        {
          if ( v6 >= v20 )
            goto LABEL_29;
          v22 = 0;
          v7 = v21;
          v8 = *(int (__fastcall **)(void *, _QWORD, GUID *, struct IExtensionListItem **))(*(_QWORD *)v21 + 32LL);
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v22);
          if ( v8(v7, v6, &GUID_51c82e0a_1438_4979_8d15_cc7ce56e52e4, &v22) >= 0 )
            break;
LABEL_28:
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v22);
          ++v6;
          if ( v2 )
            goto LABEL_29;
        }
        lpString2 = 0;
        v18 = 0;
        v19 = 0;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&lpString2);
        v18 = -1;
        v19 = -1;
        if ( (int)GetAppIdForExtensionListItem(v22, (unsigned __int16 **)&lpString2) < 0 )
        {
LABEL_27:
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&lpString2);
          goto LABEL_28;
        }
        LODWORD(v9) = v18;
        if ( v18 == -1 )
        {
          if ( lpString2 )
          {
            v9 = -1;
            do
              ++v9;
            while ( lpString2[v9] );
          }
          else
          {
            LODWORD(v9) = 0;
          }
        }
        v10 = &pszDefault;
        if ( lpString2 )
          v10 = lpString2;
        v11 = v10 != 0 ? v9 : 0;
        v12 = &pszDefault;
        if ( v10 )
          v12 = v10;
        v13 = *((_QWORD *)this + 21);
        if ( v13 == -1 )
        {
          v14 = *((_QWORD *)this + 20);
          if ( v14 )
          {
            v13 = -1;
            do
              ++v13;
            while ( *(_WORD *)(v14 + 2 * v13) );
            v15 = (const WCHAR *)*((_QWORD *)this + 20);
            goto LABEL_26;
          }
          LODWORD(v13) = 0;
        }
        else
        {
          v15 = (const WCHAR *)*((_QWORD *)this + 20);
          if ( v15 )
          {
LABEL_26:
            v2 = CompareStringOrdinal(v15, v13, v12, v11, 1) == 2;
            goto LABEL_27;
          }
        }
        v15 = &pszDefault;
        goto LABEL_26;
      }
    }
LABEL_29:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v21);
  }
  return v2;
}

```

## disassembly

```asm
0x18005ef4c  mov     [rsp-38h+arg_18], rbx
0x18005ef51  push    rbp
0x18005ef52  push    rsi
0x18005ef53  push    rdi
0x18005ef54  push    r12
0x18005ef56  push    r13
0x18005ef58  push    r14
0x18005ef5a  push    r15
0x18005ef5c  mov     rbp, rsp
0x18005ef5f  sub     rsp, 50h
0x18005ef63  mov     r14, rcx
0x18005ef66  xor     r12d, r12d
0x18005ef69  mov     sil, r12b
0x18005ef6c  cmp     [rcx+0A0h], r12
0x18005ef73  jz      loc_18005F0F9
0x18005ef79  mov     [rbp+arg_8], r12
0x18005ef7d  lea     rcx, [rbp+arg_8]
0x18005ef81  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005ef86  lea     r9, [rbp+arg_8]; void **
0x18005ef8a  call    ?CreateInstance@CExtensionList@@SAJPEBG0AEBU_GUID@@PEAPEAX@Z; CExtensionList::CreateInstance(ushort const *,ushort const *,_GUID const &,void * *)
0x18005ef8f  test    eax, eax
0x18005ef91  js      loc_18005F0F0
0x18005ef97  mov     [rbp+arg_0], r12d
0x18005ef9b  mov     rcx, [rbp+arg_8]
0x18005ef9f  mov     rax, [rcx]
0x18005efa2  lea     rdx, [rbp+arg_0]
0x18005efa6  mov     rax, [rax+18h]
0x18005efaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005efaf  test    eax, eax
0x18005efb1  js      loc_18005F0F0
0x18005efb7  mov     r15d, r12d
0x18005efba  or      r13, 0FFFFFFFFFFFFFFFFh
0x18005efbe  cmp     r15d, [rbp+arg_0]
0x18005efc2  jnb     loc_18005F0F0
0x18005efc8  mov     [rbp+arg_10], r12
0x18005efcc  mov     rdi, [rbp+arg_8]
0x18005efd0  mov     rax, [rdi]
0x18005efd3  mov     rbx, [rax+20h]
0x18005efd7  lea     rcx, [rbp+arg_10]
0x18005efdb  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005efe0  lea     r9, [rbp+arg_10]
0x18005efe4  lea     r8, _GUID_51c82e0a_1438_4979_8d15_cc7ce56e52e4
0x18005efeb  mov     edx, r15d
0x18005efee  mov     rcx, rdi
0x18005eff1  mov     rax, rbx
0x18005eff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eff9  test    eax, eax
0x18005effb  js      loc_18005F0DB
0x18005f001  mov     [rbp+lpString2], r12
0x18005f005  mov     [rbp+var_18], r12
0x18005f009  mov     [rbp+var_10], r12
0x18005f00d  lea     rcx, [rbp+lpString2]
0x18005f011  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005f016  mov     [rbp+var_18], r13
0x18005f01a  mov     [rbp+var_10], r13
0x18005f01e  lea     rdx, [rbp+lpString2]; unsigned __int16 **
0x18005f022  mov     rcx, [rbp+arg_10]; struct IExtensionListItem *
0x18005f026  call    ?GetAppIdForExtensionListItem@@YAJPEAUIExtensionListItem@@PEAPEAG@Z; GetAppIdForExtensionListItem(IExtensionListItem *,ushort * *)
0x18005f02b  test    eax, eax
0x18005f02d  js      loc_18005F0D1
0x18005f033  mov     rdx, [rbp+var_18]
0x18005f037  mov     rax, [rbp+lpString2]
0x18005f03b  cmp     rdx, r13
0x18005f03e  jnz     short loc_18005F057
0x18005f040  test    rax, rax
0x18005f043  jz      short loc_18005F054
0x18005f045  mov     rdx, r13
0x18005f048  inc     rdx
0x18005f04b  cmp     [rax+rdx*2], r12w
0x18005f050  jnz     short loc_18005F048
0x18005f052  jmp     short loc_18005F057
0x18005f054  mov     rdx, r12
0x18005f057  lea     r10, pszDefault
0x18005f05e  mov     rcx, r10
0x18005f061  test    rax, rax
0x18005f064  cmovnz  rcx, rax
0x18005f068  mov     rax, rcx
0x18005f06b  neg     rax
0x18005f06e  sbb     r9d, r9d
0x18005f071  and     r9d, edx; cchCount2
0x18005f074  mov     r8, r10
0x18005f077  test    rcx, rcx
0x18005f07a  cmovnz  r8, rcx; lpString2
0x18005f07e  mov     rdx, [r14+0A8h]; cchCount1
0x18005f085  cmp     rdx, r13
0x18005f088  jnz     short loc_18005F0AD
0x18005f08a  mov     rax, [r14+0A0h]
0x18005f091  test    rax, rax
0x18005f094  jz      short loc_18005F0A8
0x18005f096  mov     rdx, r13
0x18005f099  inc     rdx
0x18005f09c  cmp     [rax+rdx*2], r12w
0x18005f0a1  jnz     short loc_18005F099
0x18005f0a3  mov     rcx, rax
0x18005f0a6  jmp     short loc_18005F0BC
0x18005f0a8  mov     rdx, r12
0x18005f0ab  jmp     short loc_18005F0B9
0x18005f0ad  mov     rcx, [r14+0A0h]
0x18005f0b4  test    rcx, rcx
0x18005f0b7  jnz     short loc_18005F0BC
0x18005f0b9  mov     rcx, r10; lpString1
0x18005f0bc  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x18005f0c4  call    cs:__imp_CompareStringOrdinal
0x18005f0ca  cmp     eax, 2
0x18005f0cd  setz    sil
0x18005f0d1  lea     rcx, [rbp+lpString2]
0x18005f0d5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005f0da  nop
0x18005f0db  lea     rcx, [rbp+arg_10]
0x18005f0df  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005f0e4  inc     r15d
0x18005f0e7  test    sil, sil
0x18005f0ea  jz      loc_18005EFBE
0x18005f0f0  lea     rcx, [rbp+arg_8]
0x18005f0f4  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005f0f9  mov     al, sil
0x18005f0fc  mov     rbx, [rsp+50h+arg_18]
0x18005f104  add     rsp, 50h
0x18005f108  pop     r15
0x18005f10a  pop     r14
0x18005f10c  pop     r13
0x18005f10e  pop     r12
0x18005f110  pop     rdi
0x18005f111  pop     rsi
0x18005f112  pop     rbp
0x18005f113  retn
```
