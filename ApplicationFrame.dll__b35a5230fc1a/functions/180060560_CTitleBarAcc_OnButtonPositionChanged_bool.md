# CTitleBarAcc::OnButtonPositionChanged(bool)

- ea: `0x180060560`
- end: `0x1800609ae`
- name: `?OnButtonPositionChanged@CTitleBarAcc@@UEAAX_N@Z`
- size: `1102`
- prototype: `void __fastcall(CTitleBarAcc *__hidden this, bool)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003e30`
- `0x180004c98`
- `0x18001df90`
- `0x18001e260`
- `0x18001e4b8`
- `0x180028ab4`
- `0x18002bbb0`
- `0x18002c848`
- `0x18002f880`
- `0x18002fb30`
- `0x180030f80`
- `0x180038890`
- `0x180043c30`
- `0x180046b30`
- `0x18005be70`
- `0x180060560`
- `0x180072010`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180060659`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180060659`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x180060671`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x180060684`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x180060697`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x1800606aa`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x1800606bd`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x1800606d0`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x1800606e3`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x1800606f6`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x180060709`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18006071c`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x180060671`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x180060684`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x180060697`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x1800606aa`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x1800606bd`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x1800606d0`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x1800606e3`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x1800606f6`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x180060709`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18006071c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CTitleBarAcc::OnButtonPositionChanged(CTitleBarAcc *this, char a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rax
  int RestoreButtonPart; // esi
  unsigned __int64 v7; // r14
  __int64 v8; // rbx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int128 v18; // xmm0
  __int64 v19; // rcx
  __int64 *v20; // rbx
  __int64 v21; // rdi
  __int64 **v22; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 *v25; // rbx
  char IsEnabled; // al
  __int64 v27; // r8
  __int64 **v28; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  int v31; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v32; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v33; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v34[8]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v35[3]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v36[16]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v37; // [rsp+78h] [rbp-88h] BYREF
  __int64 v38; // [rsp+88h] [rbp-78h] BYREF
  __int128 v39; // [rsp+90h] [rbp-70h] BYREF
  struct tagPOINT v40[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct tagPOINT v41[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct tagPOINT v42[2]; // [rsp+C0h] [rbp-40h] BYREF
  struct tagPOINT v43[2]; // [rsp+D0h] [rbp-30h] BYREF
  struct tagPOINT v44[2]; // [rsp+100h] [rbp+0h] BYREF
  struct tagPOINT v45[2]; // [rsp+110h] [rbp+10h] BYREF
  struct tagPOINT v46[2]; // [rsp+120h] [rbp+20h] BYREF
  struct tagPOINT Points; // [rsp+130h] [rbp+30h] BYREF
  struct tagPOINT v48[2]; // [rsp+140h] [rbp+40h] BYREF

  memset(v35, 0, sizeof(v35));
  v33 = 0;
  v4 = operator new(0x38u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  *(_QWORD *)&v33 = v4;
  v32 = 0;
  v5 = operator new(0x30u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  *(_QWORD *)&v32 = v5;
  Microsoft::WRL::Wrappers::SRWLock::LockShared(v34, (char *)this - 8);
  if ( *((_QWORD *)this + 5) )
  {
    if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                (__int64)v35,
                (_QWORD *)this + 8) >= 0 )
    {
      RestoreButtonPart = CTitleBarAcc::_GetRestoreButtonPart((char *)this - 136);
      v31 = RestoreButtonPart;
      TITLE_BAR_HITTEST_RECTS::TITLE_BAR_HITTEST_RECTS((TITLE_BAR_HITTEST_RECTS *)v40);
      (*(void (__fastcall **)(_QWORD, struct tagPOINT *))(**((_QWORD **)this + 11) + 208LL))(
        *((_QWORD *)this + 11),
        v40);
      SetRectEmpty((LPRECT)this - 5);
      MapWindowPoints(*((HWND *)this + 5), 0, (LPPOINT)this - 10, 2u);
      MapWindowPoints(*((HWND *)this + 5), 0, &Points, 2u);
      MapWindowPoints(*((HWND *)this + 5), 0, v43, 2u);
      MapWindowPoints(*((HWND *)this + 5), 0, v44, 2u);
      MapWindowPoints(*((HWND *)this + 5), 0, v45, 2u);
      MapWindowPoints(*((HWND *)this + 5), 0, v40, 2u);
      MapWindowPoints(*((HWND *)this + 5), 0, v41, 2u);
      MapWindowPoints(*((HWND *)this + 5), 0, v42, 2u);
      MapWindowPoints(*((HWND *)this + 5), 0, v46, 2u);
      MapWindowPoints(*((HWND *)this + 5), 0, v48, 2u);
      v7 = *((_QWORD *)this + 13);
      v8 = 0;
      if ( v7 )
      {
        while ( 1 )
        {
          v37 = 0;
          v9 = *(_QWORD *)(*((_QWORD *)this + 12) + 8 * v8);
          v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 48LL))(v9) - 3;
          if ( !v10 )
          {
            v18 = *(_OWORD *)&v40[0].x;
            goto LABEL_23;
          }
          v11 = v10 - 1;
          if ( !v11 )
          {
            v18 = *(_OWORD *)&v41[0].x;
            goto LABEL_23;
          }
          v12 = v11 - 1;
          if ( !v12 )
          {
            v18 = *(_OWORD *)&v42[0].x;
            goto LABEL_23;
          }
          v13 = v12 - 1;
          if ( !v13 )
          {
            v18 = *(_OWORD *)&v43[0].x;
            goto LABEL_23;
          }
          v14 = v13 - 1;
          if ( !v14 || (v15 = v14 - 1) == 0 )
          {
            v19 = *(_QWORD *)(*((_QWORD *)this + 12) + 8 * v8);
            if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v19 + 48LL))(v19) != RestoreButtonPart )
            {
              std::_Tree<std::_Tmap_traits<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,enum TitleBarPart,std::less<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,std::allocator<std::pair<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const,enum TitleBarPart>>,0>>::_Emplace<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> &,enum TitleBarPart const &>(
                &v32,
                v36,
                *((_QWORD *)this + 12) + 8 * v8,
                &v31);
              RestoreButtonPart = v31;
            }
            v18 = *(_OWORD *)&v45[0].x;
            goto LABEL_23;
          }
          v16 = v15 - 3;
          if ( !v16 )
          {
            v18 = *(_OWORD *)&v44[0].x;
            goto LABEL_23;
          }
          v17 = v16 - 1;
          if ( !v17 )
            break;
          if ( v17 == 3 )
          {
            v18 = *(_OWORD *)&v48[0].x;
LABEL_23:
            v37 = v18;
            std::_Tree<std::_Tmap_traits<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,Geometry::CRect,std::less<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,std::allocator<std::pair<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const,Geometry::CRect>>,0>>::emplace<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> &,Geometry::CRect &>(
              &v33,
              &v38,
              *((_QWORD *)this + 12) + 8 * v8,
              &v37);
          }
          if ( ++v8 >= v7 )
            goto LABEL_25;
        }
        v18 = *(_OWORD *)&v46[0].x;
        goto LABEL_23;
      }
    }
  }
LABEL_25:
  Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v34);
  v20 = *(__int64 **)v32;
  while ( !*((_BYTE *)v20 + 25) )
  {
    *(_QWORD *)&v37 = v20[4];
    v21 = v37;
    Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(&v37);
    DWORD2(v37) = *((_DWORD *)v20 + 10);
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v21 + 56LL))(v21, DWORD2(v37), v35[0]);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v37);
    v22 = (__int64 **)v20[2];
    if ( *((_BYTE *)v22 + 25) )
    {
      for ( i = (__int64 *)v20[1]; !*((_BYTE *)i + 25) && v20 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v20 = i;
      v20 = i;
    }
    else
    {
      v20 = (__int64 *)v20[2];
      for ( j = *v22; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v20 = j;
    }
  }
  v25 = *(__int64 **)v33;
  while ( !*((_BYTE *)v25 + 25) )
  {
    v38 = v25[4];
    Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(&v38);
    v39 = *(_OWORD *)(v25 + 5);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::GetImpl'::`2'::impl);
    LOBYTE(v27) = a2;
    if ( !IsEnabled )
      LOBYTE(v27) = 1;
    (*(void (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v38 + 64LL))(v38, &v39, v27);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v38);
    v28 = (__int64 **)v25[2];
    if ( *((_BYTE *)v28 + 25) )
    {
      for ( k = (__int64 *)v25[1]; !*((_BYTE *)k + 25) && v25 == (__int64 *)k[2]; k = (__int64 *)k[1] )
        v25 = k;
      v25 = k;
    }
    else
    {
      v25 = (__int64 *)v25[2];
      for ( m = *v28; !*((_BYTE *)m + 25); m = (__int64 *)*m )
        v25 = m;
    }
  }
  std::map<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,enum TitleBarPart>::~map<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,enum TitleBarPart>(&v32);
  std::_Tree<std::_Tmap_traits<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,Geometry::CRect,std::less<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,std::allocator<std::pair<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const,Geometry::CRect>>,0>>::~_Tree<std::_Tmap_traits<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,Geometry::CRect,std::less<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,std::allocator<std::pair<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const,Geometry::CRect>>,0>>(&v33);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v35);
}

```

## disassembly

```asm
0x180060560  mov     [rsp-8+arg_10], rbx
0x180060565  push    rbp
0x180060566  push    rsi
0x180060567  push    rdi
0x180060568  push    r12
0x18006056a  push    r13
0x18006056c  push    r14
0x18006056e  push    r15
0x180060570  lea     rbp, [rsp-70h]
0x180060575  sub     rsp, 170h
0x18006057c  mov     rax, cs:__security_cookie
0x180060583  xor     rax, rsp
0x180060586  mov     [rbp+0A0h+var_40], rax
0x18006058a  mov     r15b, dl
0x18006058d  mov     rdi, rcx
0x180060590  xor     r12d, r12d
0x180060593  mov     [rsp+1A0h+var_150], r12
0x180060598  mov     [rsp+1A0h+var_148], r12
0x18006059d  mov     [rsp+1A0h+var_140], r12
0x1800605a2  xorps   xmm0, xmm0
0x1800605a5  movdqu  [rsp+1A0h+var_168], xmm0
0x1800605ab  lea     ecx, [r12+38h]; Size
0x1800605b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800605b5  mov     [rax], rax
0x1800605b8  mov     [rax+8], rax
0x1800605bc  mov     [rax+10h], rax
0x1800605c0  mov     word ptr [rax+18h], 101h
0x1800605c6  mov     qword ptr [rsp+1A0h+var_168], rax
0x1800605cb  xorps   xmm0, xmm0
0x1800605ce  movdqu  [rsp+1A0h+var_178], xmm0
0x1800605d4  lea     ecx, [r12+30h]; Size
0x1800605d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800605de  mov     [rax], rax
0x1800605e1  mov     [rax+8], rax
0x1800605e5  mov     [rax+10h], rax
0x1800605e9  mov     word ptr [rax+18h], 101h
0x1800605ef  mov     qword ptr [rsp+1A0h+var_178], rax
0x1800605f4  lea     rdx, [rdi-8]
0x1800605f8  lea     rcx, [rsp+1A0h+var_158]
0x1800605fd  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180060602  nop
0x180060603  cmp     [rdi+28h], r12
0x180060607  jz      loc_18006081F
0x18006060d  lea     rdx, [rdi+40h]
0x180060611  lea     rcx, [rsp+1A0h+var_150]
0x180060616  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x18006061b  test    eax, eax
0x18006061d  js      loc_18006081F
0x180060623  lea     rcx, [rdi-88h]
0x18006062a  call    ?_GetRestoreButtonPart@CTitleBarAcc@@AEAA?AW4TitleBarPart@@XZ; CTitleBarAcc::_GetRestoreButtonPart(void)
0x18006062f  mov     esi, eax
0x180060631  mov     [rsp+1A0h+var_180], eax
0x180060635  lea     rcx, [rbp+0A0h+var_100]; this
0x180060639  call    ??0TITLE_BAR_HITTEST_RECTS@@QEAA@XZ; TITLE_BAR_HITTEST_RECTS::TITLE_BAR_HITTEST_RECTS(void)
0x18006063e  mov     rcx, [rdi+58h]
0x180060642  mov     rdx, [rcx]
0x180060645  mov     rax, [rdx+0D0h]
0x18006064c  lea     rdx, [rbp+0A0h+var_100]
0x180060650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060655  lea     rcx, [rdi-50h]; lprc
0x180060659  call    cs:__imp_SetRectEmpty
0x18006065f  lea     r14d, [r12+2]
0x180060664  mov     r9d, r14d; cPoints
0x180060667  lea     r8, [rdi-50h]; lpPoints
0x18006066b  xor     edx, edx; hWndTo
0x18006066d  mov     rcx, [rdi+28h]; hWndFrom
0x180060671  call    cs:__imp_MapWindowPoints
0x180060677  mov     r9d, r14d; cPoints
0x18006067a  lea     r8, [rbp+0A0h+Points]; lpPoints
0x18006067e  xor     edx, edx; hWndTo
0x180060680  mov     rcx, [rdi+28h]; hWndFrom
0x180060684  call    cs:__imp_MapWindowPoints
0x18006068a  mov     r9d, r14d; cPoints
0x18006068d  lea     r8, [rbp+0A0h+var_D0]; lpPoints
0x180060691  xor     edx, edx; hWndTo
0x180060693  mov     rcx, [rdi+28h]; hWndFrom
0x180060697  call    cs:__imp_MapWindowPoints
0x18006069d  mov     r9d, r14d; cPoints
0x1800606a0  lea     r8, [rbp+0A0h+var_A0]; lpPoints
0x1800606a4  xor     edx, edx; hWndTo
0x1800606a6  mov     rcx, [rdi+28h]; hWndFrom
0x1800606aa  call    cs:__imp_MapWindowPoints
0x1800606b0  mov     r9d, r14d; cPoints
0x1800606b3  lea     r8, [rbp+0A0h+var_90]; lpPoints
0x1800606b7  xor     edx, edx; hWndTo
0x1800606b9  mov     rcx, [rdi+28h]; hWndFrom
0x1800606bd  call    cs:__imp_MapWindowPoints
0x1800606c3  mov     r9d, r14d; cPoints
0x1800606c6  lea     r8, [rbp+0A0h+var_100]; lpPoints
0x1800606ca  xor     edx, edx; hWndTo
0x1800606cc  mov     rcx, [rdi+28h]; hWndFrom
0x1800606d0  call    cs:__imp_MapWindowPoints
0x1800606d6  mov     r9d, r14d; cPoints
0x1800606d9  lea     r8, [rbp+0A0h+var_F0]; lpPoints
0x1800606dd  xor     edx, edx; hWndTo
0x1800606df  mov     rcx, [rdi+28h]; hWndFrom
0x1800606e3  call    cs:__imp_MapWindowPoints
0x1800606e9  mov     r9d, r14d; cPoints
0x1800606ec  lea     r8, [rbp+0A0h+var_E0]; lpPoints
0x1800606f0  xor     edx, edx; hWndTo
0x1800606f2  mov     rcx, [rdi+28h]; hWndFrom
0x1800606f6  call    cs:__imp_MapWindowPoints
0x1800606fc  mov     r9d, r14d; cPoints
0x1800606ff  lea     r8, [rbp+0A0h+var_80]; lpPoints
0x180060703  xor     edx, edx; hWndTo
0x180060705  mov     rcx, [rdi+28h]; hWndFrom
0x180060709  call    cs:__imp_MapWindowPoints
0x18006070f  mov     r9d, r14d; cPoints
0x180060712  lea     r8, [rbp+0A0h+var_60]; lpPoints
0x180060716  xor     edx, edx; hWndTo
0x180060718  mov     rcx, [rdi+28h]; hWndFrom
0x18006071c  call    cs:__imp_MapWindowPoints
0x180060722  mov     r14, [rdi+68h]
0x180060726  mov     ebx, r12d
0x180060729  test    r14, r14
0x18006072c  jz      loc_18006081F
0x180060732  lea     r13, [rsp+1A0h+var_128]
0x180060737  xorps   xmm0, xmm0
0x18006073a  movups  xmmword ptr [r13+0], xmm0
0x18006073f  mov     rax, [rdi+60h]
0x180060743  mov     rcx, [rax+rbx*8]
0x180060747  mov     rax, [rcx]
0x18006074a  mov     rax, [rax+30h]
0x18006074e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060753  sub     eax, 3
0x180060756  jz      loc_1800607EE
0x18006075c  sub     eax, 1
0x18006075f  jz      loc_1800607E8
0x180060765  sub     eax, 1
0x180060768  jz      short loc_1800607E2
0x18006076a  sub     eax, 1
0x18006076d  jz      short loc_1800607DC
0x18006076f  sub     eax, 1
0x180060772  jz      short loc_18006079E
0x180060774  sub     eax, 1
0x180060777  jz      short loc_18006079E
0x180060779  sub     eax, 3
0x18006077c  jz      short loc_180060798
0x18006077e  sub     eax, 1
0x180060781  jz      short loc_180060792
0x180060783  cmp     eax, 3
0x180060786  jnz     loc_180060813
0x18006078c  movaps  xmm0, xmmword ptr [rbp+0A0h+var_60.x]
0x180060790  jmp     short loc_1800607F2
0x180060792  movaps  xmm0, xmmword ptr [rbp+0A0h+var_80.x]
0x180060796  jmp     short loc_1800607F2
0x180060798  movaps  xmm0, xmmword ptr [rbp+0A0h+var_A0.x]
0x18006079c  jmp     short loc_1800607F2
0x18006079e  mov     rax, [rdi+60h]
0x1800607a2  mov     rcx, [rax+rbx*8]
0x1800607a6  mov     rax, [rcx]
0x1800607a9  mov     rax, [rax+30h]
0x1800607ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800607b2  cmp     eax, esi
0x1800607b4  jz      short loc_1800607D6
0x1800607b6  mov     rax, [rdi+60h]
0x1800607ba  lea     r8, [rax+rbx*8]
0x1800607be  lea     r9, [rsp+1A0h+var_180]
0x1800607c3  lea     rdx, [rsp+1A0h+var_138]
0x1800607c8  lea     rcx, [rsp+1A0h+var_178]
0x1800607cd  call    ??$_Emplace@AEAV?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@AEBW4TitleBarPart@@@?$_Tree@V?$_Tmap_traits@V?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@W4TitleBarPart@@U?$less@V?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBV?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@W4TitleBarPart@@@std@@@6@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@W4TitleBarPart@@@std@@PEAX@std@@_N@1@AEAV?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@AEBW4TitleBarPart@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,TitleBarPart,std::less<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,std::allocator<std::pair<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const,TitleBarPart>>,0>>::_Emplace<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> &,TitleBarPart const &>(Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> &,TitleBarPart const &)
0x1800607d2  mov     esi, [rsp+1A0h+var_180]
0x1800607d6  movaps  xmm0, xmmword ptr [rbp+0A0h+var_90.x]
0x1800607da  jmp     short loc_1800607F2
0x1800607dc  movaps  xmm0, xmmword ptr [rbp+0A0h+var_D0.x]
0x1800607e0  jmp     short loc_1800607F2
0x1800607e2  movaps  xmm0, xmmword ptr [rbp+0A0h+var_E0.x]
0x1800607e6  jmp     short loc_1800607F2
0x1800607e8  movaps  xmm0, xmmword ptr [rbp+0A0h+var_F0.x]
0x1800607ec  jmp     short loc_1800607F2
0x1800607ee  movaps  xmm0, xmmword ptr [rbp+0A0h+var_100.x]
0x1800607f2  movdqu  [rsp+1A0h+var_128], xmm0
0x1800607f8  mov     rax, [rdi+60h]
0x1800607fc  lea     r8, [rax+rbx*8]
0x180060800  lea     r9, [rsp+1A0h+var_128]
0x180060805  lea     rdx, [rbp+0A0h+var_118]
0x180060809  lea     rcx, [rsp+1A0h+var_168]
0x18006080e  call    ??$emplace@AEAV?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@AEAUCRect@Geometry@@@?$_Tree@V?$_Tmap_traits@V?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@UCRect@Geometry@@U?$less@V?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBV?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@UCRect@Geometry@@@std@@@7@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@UCRect@Geometry@@@std@@@std@@@std@@@std@@_N@1@AEAV?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@AEAUCRect@Geometry@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,Geometry::CRect,std::less<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,std::allocator<std::pair<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const,Geometry::CRect>>,0>>::emplace<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> &,Geometry::CRect &>(Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> &,Geometry::CRect &)
0x180060813  inc     rbx
0x180060816  cmp     rbx, r14
0x180060819  jb      loc_180060737
0x18006081f  lea     rcx, [rsp+1A0h+var_158]; this
0x180060824  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x180060829  mov     rbx, qword ptr [rsp+1A0h+var_178]
0x18006082e  mov     rbx, [rbx]
0x180060831  cmp     [rbx+19h], r12b
0x180060835  jnz     loc_1800608BB
0x18006083b  mov     rdi, [rbx+20h]
0x18006083f  mov     qword ptr [rsp+1A0h+var_128], rdi
0x180060844  lea     rcx, [rsp+1A0h+var_128]
0x180060849  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x18006084e  mov     edx, [rbx+28h]
0x180060851  mov     dword ptr [rbp+0A0h+var_128+8], edx
0x180060854  mov     rax, [rdi]
0x180060857  mov     r8, [rsp+1A0h+var_150]
0x18006085c  mov     rcx, rdi
0x18006085f  mov     rax, [rax+38h]
0x180060863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060868  nop
0x180060869  lea     rcx, [rsp+1A0h+var_128]
0x18006086e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180060873  mov     rcx, [rbx+10h]
0x180060877  cmp     [rcx+19h], r12b
0x18006087b  jz      short loc_18006089B
0x18006087d  mov     rax, [rbx+8]
0x180060881  jmp     short loc_180060890
0x180060883  cmp     rbx, [rax+10h]
0x180060887  jnz     short loc_180060896
0x180060889  mov     rbx, rax
0x18006088c  mov     rax, [rax+8]
0x180060890  cmp     [rax+19h], r12b
0x180060894  jz      short loc_180060883
0x180060896  mov     rbx, rax
0x180060899  jmp     short loc_180060831
0x18006089b  mov     rbx, rcx
0x18006089e  mov     rcx, [rcx]
0x1800608a1  cmp     [rcx+19h], r12b
0x1800608a5  jnz     short loc_180060831
0x1800608a7  mov     rbx, rcx
0x1800608aa  mov     rax, [rcx]
0x1800608ad  mov     rcx, rax
0x1800608b0  cmp     [rax+19h], r12b
0x1800608b4  jz      short loc_1800608A7
0x1800608b6  jmp     loc_180060831
0x1800608bb  mov     rbx, qword ptr [rsp+1A0h+var_168]
0x1800608c0  mov     rbx, [rbx]
0x1800608c3  cmp     [rbx+19h], r12b
0x1800608c7  jnz     loc_180060967
0x1800608cd  mov     rax, [rbx+20h]
0x1800608d1  mov     [rbp+0A0h+var_118], rax
0x1800608d5  lea     rcx, [rbp+0A0h+var_118]
0x1800608d9  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x1800608de  movups  xmm0, xmmword ptr [rbx+28h]
0x1800608e2  movdqu  [rbp+0A0h+var_110], xmm0
0x1800608e7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode> `wil::Feature<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::GetImpl(void)'::`2'::impl
0x1800608ee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::__private_IsEnabled(void)
0x1800608f3  mov     rcx, [rbp+0A0h+var_118]
0x1800608f7  lea     rdx, [rbp+0A0h+var_110]
0x1800608fb  test    al, al
0x1800608fd  mov     rax, [rcx]
0x180060900  mov     rax, [rax+40h]
0x180060904  mov     r8b, r15b
0x180060907  jnz     short loc_18006090C
0x180060909  mov     r8b, 1
0x18006090c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060911  nop
0x180060912  lea     rcx, [rbp+0A0h+var_118]
0x180060916  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18006091b  mov     rcx, [rbx+10h]
0x18006091f  cmp     [rcx+19h], r12b
0x180060923  jz      short loc_180060943
0x180060925  mov     rax, [rbx+8]
0x180060929  jmp     short loc_180060938
0x18006092b  cmp     rbx, [rax+10h]
0x18006092f  jnz     short loc_18006093E
0x180060931  mov     rbx, rax
0x180060934  mov     rax, [rax+8]
0x180060938  cmp     [rax+19h], r12b
0x18006093c  jz      short loc_18006092B
0x18006093e  mov     rbx, rax
0x180060941  jmp     short loc_1800608C3
0x180060943  mov     rbx, rcx
0x180060946  mov     rcx, [rcx]
0x180060949  cmp     [rcx+19h], r12b
0x18006094d  jnz     loc_1800608C3
0x180060953  mov     rbx, rcx
0x180060956  mov     rax, [rcx]
0x180060959  mov     rcx, rax
0x18006095c  cmp     [rax+19h], r12b
0x180060960  jz      short loc_180060953
0x180060962  jmp     loc_1800608C3
0x180060967  lea     rcx, [rsp+1A0h+var_178]
0x18006096c  call    ??1?$map@V?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@W4TitleBarPart@@U?$less@V?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBV?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@W4TitleBarPart@@@std@@@6@@std@@QEAA@XZ; std::map<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,TitleBarPart>::~map<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,TitleBarPart>(void)
0x180060971  nop
0x180060972  lea     rcx, [rsp+1A0h+var_168]
0x180060977  call    ??1?$_Tree@V?$_Tmap_traits@V?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@UCRect@Geometry@@U?$less@V?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBV?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@UCRect@Geometry@@@std@@@7@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,Geometry::CRect,std::less<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,std::allocator<std::pair<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const,Geometry::CRect>>,0>>::~_Tree<std::_Tmap_traits<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,Geometry::CRect,std::less<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,std::allocator<std::pair<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const,Geometry::CRect>>,0>>(void)
0x18006097c  nop
0x18006097d  lea     rcx, [rsp+1A0h+var_150]
0x180060982  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180060987  mov     rcx, [rbp+0A0h+var_40]
0x18006098b  xor     rcx, rsp; StackCookie
0x18006098e  call    __security_check_cookie
0x180060993  mov     rbx, [rsp+1A0h+arg_10]
0x18006099b  add     rsp, 170h
0x1800609a2  pop     r15
0x1800609a4  pop     r14
0x1800609a6  pop     r13
0x1800609a8  pop     r12
0x1800609aa  pop     rdi
0x1800609ab  pop     rsi
0x1800609ac  pop     rbp
0x1800609ad  retn
```
