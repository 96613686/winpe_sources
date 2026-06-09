# Windows::UI::Input::Inking::CInkStroke::SaveInkPointTimestampToInkStrokeDisp(IInkStrokeDisp *)

- ea: `0x180054ee0`
- end: `0x1800550d7`
- name: `?SaveInkPointTimestampToInkStrokeDisp@CInkStroke@Inking@Input@UI@Windows@@UEAAJPEAUIInkStrokeDisp@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::CInkStroke *__hidden this, struct IInkStrokeDisp *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800101bc`
- `0x18001043c`
- `0x180054ee0`
- `0x180060c60`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800550c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800550c0`
- `OLEAUT32!__imp_SysAllocString` at `0x180054f4b`
- `OLEAUT32!__imp_SysAllocString` at `0x180054f4b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800550a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800550a1`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180055091`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180055091`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180054fc6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180054fc6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180054ffb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180054ffb`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180054fa5`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180054fa5`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::CInkStroke::SaveInkPointTimestampToInkStrokeDisp(
        Windows::UI::Input::Inking::CInkStroke *this,
        struct IInkStrokeDisp *a2)
{
  HRESULT InkPointTimestampAtIndex; // edi
  struct IInkStrokeDispVtbl *lpVtbl; // rax
  HRESULT (__stdcall *get_ExtendedProperties)(IInkStrokeDisp *, IInkExtendedProperties **); // rbx
  OLECHAR *v7; // r12
  unsigned int v8; // r14d
  __int64 v9; // rcx
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v11; // r15
  _QWORD *v12; // rdi
  __int64 v13; // rax
  __int64 (__fastcall *v14)(_QWORD *, OLECHAR *, __int128 *, __int64 *); // rbx
  __int64 v15; // rcx
  __int64 v16; // rbx
  PSRWLOCK SRWLock[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v19; // [rsp+40h] [rbp-20h] BYREF
  __int64 v20; // [rsp+50h] [rbp-10h]
  void *ppvData; // [rsp+A0h] [rbp+40h] BYREF
  _QWORD *v22; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v23; // [rsp+B8h] [rbp+58h] BYREF

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, (char *)this + 280);
  InkPointTimestampAtIndex = 0;
  if ( *((_BYTE *)this + 148) )
  {
    lpVtbl = a2->lpVtbl;
    v22 = 0;
    get_ExtendedProperties = lpVtbl->get_ExtendedProperties;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
    InkPointTimestampAtIndex = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, _QWORD **))get_ExtendedProperties)(
                                 a2,
                                 &v22);
    if ( InkPointTimestampAtIndex < 0 )
    {
LABEL_21:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
      goto LABEL_22;
    }
    v7 = SysAllocString(L"{65D6C92F-E2F0-4DAA-9316-C52D3ECFA0DE}");
    if ( !v7 )
    {
      InkPointTimestampAtIndex = -2147024882;
      goto LABEL_21;
    }
    if ( *((_BYTE *)this + 149) )
    {
      v8 = 1;
    }
    else
    {
      v9 = *((_QWORD *)this + 31);
      LODWORD(ppvData) = 0;
      InkPointTimestampAtIndex = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v9 + 56LL))(v9, &ppvData);
      if ( InkPointTimestampAtIndex < 0 )
      {
LABEL_19:
        SysFreeString(v7);
        goto LABEL_21;
      }
      v8 = (unsigned int)ppvData;
    }
    Vector = SafeArrayCreateVector(0x15u, 0, v8 + 1);
    v11 = Vector;
    if ( Vector )
    {
      ppvData = 0;
      InkPointTimestampAtIndex = SafeArrayAccessData(Vector, &ppvData);
      if ( InkPointTimestampAtIndex < 0 )
      {
LABEL_17:
        SafeArrayDestroy(v11);
      }
      else
      {
        *(_QWORD *)ppvData = v8;
        if ( *((_BYTE *)this + 149) )
        {
          *((_QWORD *)ppvData + 1) = *((_QWORD *)this + 19);
        }
        else
        {
          v15 = 0;
          while ( (unsigned int)v15 < v8 )
          {
            v16 = (unsigned int)(v15 + 1);
            InkPointTimestampAtIndex = InkPointHelper::GetInkPointTimestampAtIndex(
                                         v15,
                                         *((_QWORD *)this + 31),
                                         (char *)ppvData + 8 * v16);
            v15 = (unsigned int)v16;
            if ( InkPointTimestampAtIndex < 0 )
              goto LABEL_17;
          }
        }
        InkPointTimestampAtIndex = SafeArrayUnaccessData(v11);
        if ( InkPointTimestampAtIndex >= 0 )
        {
          v12 = v22;
          v19 = 0;
          LOWORD(v19) = 8213;
          v23 = 0;
          v13 = *v22;
          *((_QWORD *)&v19 + 1) = v11;
          v14 = *(__int64 (__fastcall **)(_QWORD *, OLECHAR *, __int128 *, __int64 *))(v13 + 80);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
          v20 = 0;
          InkPointTimestampAtIndex = v14(v12, v7, &v19, &v23);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
        }
      }
    }
    else
    {
      InkPointTimestampAtIndex = -2147024882;
    }
    goto LABEL_19;
  }
LABEL_22:
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  return (unsigned int)InkPointTimestampAtIndex;
}

```

## disassembly

```asm
0x180054ee0  push    rbp
0x180054ee2  push    rbx
0x180054ee3  push    rsi
0x180054ee4  push    rdi
0x180054ee5  push    r12
0x180054ee7  push    r14
0x180054ee9  push    r15
0x180054eeb  mov     rbp, rsp
0x180054eee  sub     rsp, 60h
0x180054ef2  mov     r14, rdx
0x180054ef5  mov     rsi, rcx
0x180054ef8  lea     rdx, [rcx+118h]
0x180054eff  lea     rcx, [rbp+SRWLock]
0x180054f03  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180054f08  xor     edi, edi
0x180054f0a  cmp     [rsi+94h], dil
0x180054f11  jz      loc_1800550B7
0x180054f17  mov     rax, [r14]
0x180054f1a  lea     rcx, [rbp+arg_10]
0x180054f1e  mov     [rbp+arg_10], rdi
0x180054f22  mov     rbx, [rax+60h]
0x180054f26  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180054f2b  lea     rdx, [rbp+arg_10]
0x180054f2f  mov     rcx, r14
0x180054f32  mov     rax, rbx
0x180054f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f3a  mov     edi, eax
0x180054f3c  test    eax, eax
0x180054f3e  js      loc_1800550AE
0x180054f44  lea     rcx, a65d6c92fE2f04d; "{65D6C92F-E2F0-4DAA-9316-C52D3ECFA0DE}"
0x180054f4b  call    cs:__imp_SysAllocString
0x180054f51  mov     r12, rax
0x180054f54  test    rax, rax
0x180054f57  jz      loc_1800550A9
0x180054f5d  cmp     byte ptr [rsi+95h], 0
0x180054f64  jz      short loc_180054F6E
0x180054f66  mov     r14d, 1
0x180054f6c  jmp     short loc_180054F9A
0x180054f6e  mov     rcx, [rsi+0F8h]
0x180054f75  lea     rdx, [rbp+ppvData]
0x180054f79  mov     dword ptr [rbp+ppvData], 0
0x180054f80  mov     rax, [rcx]
0x180054f83  mov     rax, [rax+38h]
0x180054f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f8c  mov     edi, eax
0x180054f8e  test    eax, eax
0x180054f90  js      loc_18005509E
0x180054f96  mov     r14d, dword ptr [rbp+ppvData]
0x180054f9a  lea     r8d, [r14+1]; cElements
0x180054f9e  mov     ecx, 15h; vt
0x180054fa3  xor     edx, edx; lLbound
0x180054fa5  call    cs:__imp_SafeArrayCreateVector
0x180054fab  mov     r15, rax
0x180054fae  test    rax, rax
0x180054fb1  jz      loc_180055099
0x180054fb7  lea     rdx, [rbp+ppvData]; ppvData
0x180054fbb  mov     [rbp+ppvData], 0
0x180054fc3  mov     rcx, rax; psa
0x180054fc6  call    cs:__imp_SafeArrayAccessData
0x180054fcc  mov     edi, eax
0x180054fce  test    eax, eax
0x180054fd0  js      loc_18005508E
0x180054fd6  mov     rcx, [rbp+ppvData]
0x180054fda  mov     edx, r14d
0x180054fdd  mov     [rcx], rdx
0x180054fe0  cmp     byte ptr [rsi+95h], 0
0x180054fe7  jz      short loc_180055068
0x180054fe9  mov     rax, [rbp+ppvData]
0x180054fed  mov     rcx, [rsi+98h]
0x180054ff4  mov     [rax+8], rcx
0x180054ff8  mov     rcx, r15; psa
0x180054ffb  call    cs:__imp_SafeArrayUnaccessData
0x180055001  mov     edi, eax
0x180055003  test    eax, eax
0x180055005  js      loc_18005509E
0x18005500b  mov     rdi, [rbp+arg_10]
0x18005500f  lea     rcx, [rbp+arg_18]
0x180055013  xorps   xmm0, xmm0
0x180055016  mov     eax, 2015h
0x18005501b  movups  [rbp+var_20], xmm0
0x18005501f  mov     word ptr [rbp+var_20], ax
0x180055023  xor     esi, esi
0x180055025  mov     [rbp+arg_18], rsi
0x180055029  mov     rax, [rdi]
0x18005502c  mov     qword ptr [rbp+var_20+8], r15
0x180055030  mov     rbx, [rax+50h]
0x180055034  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055039  movups  xmm0, [rbp+var_20]
0x18005503d  lea     r9, [rbp+arg_18]
0x180055041  mov     [rbp+var_10], rsi
0x180055045  lea     r8, [rbp+var_20]
0x180055049  mov     rdx, r12
0x18005504c  mov     rcx, rdi
0x18005504f  movaps  [rbp+var_20], xmm0
0x180055053  mov     rax, rbx
0x180055056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005505b  lea     rcx, [rbp+arg_18]
0x18005505f  mov     edi, eax
0x180055061  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055066  jmp     short loc_18005509E
0x180055068  xor     ecx, ecx
0x18005506a  cmp     ecx, r14d
0x18005506d  jnb     short loc_180054FF8
0x18005506f  mov     rax, [rbp+ppvData]
0x180055073  lea     ebx, [rcx+1]
0x180055076  mov     rdx, [rsi+0F8h]
0x18005507d  lea     r8, [rax+rbx*8]
0x180055081  call    ?GetInkPointTimestampAtIndex@InkPointHelper@@SAJIPEAU?$IVector@PEAVInkPoint@Inking@Input@UI@Windows@@@Collections@Foundation@Windows@@PEA_K@Z; InkPointHelper::GetInkPointTimestampAtIndex(uint,Windows::Foundation::Collections::IVector<Windows::UI::Input::Inking::InkPoint *> *,unsigned __int64 *)
0x180055086  mov     edi, eax
0x180055088  mov     ecx, ebx
0x18005508a  test    eax, eax
0x18005508c  jns     short loc_18005506A
0x18005508e  mov     rcx, r15; psa
0x180055091  call    cs:__imp_SafeArrayDestroy
0x180055097  jmp     short loc_18005509E
0x180055099  mov     edi, 8007000Eh
0x18005509e  mov     rcx, r12; bstrString
0x1800550a1  call    cs:__imp_SysFreeString
0x1800550a7  jmp     short loc_1800550AE
0x1800550a9  mov     edi, 8007000Eh
0x1800550ae  lea     rcx, [rbp+arg_10]
0x1800550b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800550b7  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800550bb  test    rcx, rcx
0x1800550be  jz      short loc_1800550C6
0x1800550c0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800550c6  mov     eax, edi
0x1800550c8  add     rsp, 60h
0x1800550cc  pop     r15
0x1800550ce  pop     r14
0x1800550d0  pop     r12
0x1800550d2  pop     rdi
0x1800550d3  pop     rsi
0x1800550d4  pop     rbx
0x1800550d5  pop     rbp
0x1800550d6  retn
```
