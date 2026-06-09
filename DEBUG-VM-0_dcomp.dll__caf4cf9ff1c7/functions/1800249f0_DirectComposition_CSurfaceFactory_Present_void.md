# DirectComposition::CSurfaceFactory::Present(void)

- ea: `0x1800249f0`
- end: `0x180025188`
- name: `?Present@CSurfaceFactory@DirectComposition@@QEAAJXZ`
- size: `1944`
- prototype: `__int64 __fastcall(DirectComposition::CSurfaceFactory *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180058a08`

## callees

- `0x1800093f4`
- `0x180013528`
- `0x18001358c`
- `0x180015220`
- `0x180016208`
- `0x18001f860`
- `0x180021140`
- `0x1800240d8`
- `0x1800249f0`
- `0x180025348`
- `0x180025468`
- `0x180025538`
- `0x180025580`
- `0x180025f48`
- `0x180062b80`
- `0x1800827d0`
- `0x1800df108`
- `0x1800eb59c`
- `0x1800f6f10`
- `0x180182010`

## import_xrefs

- `win32u!NtTokenManagerCreateCompositionTokenHandle` at `0x180024f65`
- `win32u!NtTokenManagerCreateCompositionTokenHandle` at `0x180024f65`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024b20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024b4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024b20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024b4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024b12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024b3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024b12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024b3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800250c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800250c5`

## string_xrefs

- `0x1800250d7`: `onecoreuap\windows\dwm\dcomp\dll\kerneltokenfactory.cpp`
- `0x180025165`: `onecoreuap\windows\dwm\dcomp\dll\kerneltokenfactory.cpp`

## pseudocode

```c
__int64 __fastcall DirectComposition::CSurfaceFactory::Present(DirectComposition::CSurfaceFactory *this)
{
  __int64 v1; // rbx
  int v2; // r15d
  int v4; // esi
  __int64 i; // rbx
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int128 *v8; // rdx
  __int64 v9; // rsi
  __int64 v10; // rcx
  unsigned int v11; // r14d
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  void *v14; // rbx
  HANDLE v15; // rax
  __int128 *v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // r14
  int v27; // edx
  int v28; // r8d
  unsigned int v29; // r12d
  int v30; // ecx
  __int64 v31; // rax
  int v32; // r13d
  __int64 v33; // r8
  __int64 *v34; // r9
  unsigned int v35; // edx
  _QWORD *v36; // rax
  __int64 v37; // rax
  unsigned int v38; // edx
  int v39; // ecx
  __int64 v40; // rcx
  LPVOID v41; // r15
  unsigned int v42; // r12d
  LPVOID v43; // r13
  _QWORD *v44; // rbx
  int v45; // eax
  const struct DirectComposition::CDxDevice *v46; // r15
  HANDLE v47; // r12
  int v48; // eax
  int v49; // eax
  __int128 *v50; // rax
  int v51; // eax
  __int64 (__fastcall ***v52)(_QWORD, GUID *, __int128 **); // rdi
  __int64 (__fastcall *v53)(_QWORD, GUID *, __int128 **); // rbx
  int v54; // eax
  int v55; // eax
  __int128 *v56; // rcx
  __int128 *v57; // rcx
  __int64 v58; // rax
  char *v59; // [rsp+20h] [rbp-E0h]
  __int128 *v60; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v61; // [rsp+48h] [rbp-B8h] BYREF
  int v62; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-A8h]
  int v64[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v65; // [rsp+68h] [rbp-98h] BYREF
  __int128 v66; // [rsp+70h] [rbp-90h] BYREF
  __int64 v67; // [rsp+80h] [rbp-80h]
  LPVOID v68; // [rsp+90h] [rbp-70h] BYREF
  _BYTE *v69; // [rsp+98h] [rbp-68h]
  int v70; // [rsp+A0h] [rbp-60h]
  __int64 v71; // [rsp+A4h] [rbp-5Ch]
  _BYTE v72[128]; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID lpMem; // [rsp+130h] [rbp+30h] BYREF
  _BYTE *v74; // [rsp+138h] [rbp+38h]
  int v75; // [rsp+140h] [rbp+40h]
  __int64 v76; // [rsp+144h] [rbp+44h]
  _BYTE v77[384]; // [rsp+150h] [rbp+50h] BYREF
  char v78; // [rsp+2D0h] [rbp+1D0h] BYREF
  int *v79; // [rsp+2E0h] [rbp+1E0h]
  __int64 v80; // [rsp+2E8h] [rbp+1E8h]
  int *v81; // [rsp+2F0h] [rbp+1F0h]
  __int64 v82; // [rsp+2F8h] [rbp+1F8h]
  __int128 **v83; // [rsp+300h] [rbp+200h]
  __int64 v84; // [rsp+308h] [rbp+208h]
  char v85; // [rsp+310h] [rbp+210h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+278h]

  v1 = *((_QWORD *)this + 41);
  v68 = v72;
  v2 = 0;
  v70 = 16;
  v69 = v72;
  lpMem = v77;
  v74 = v77;
  v71 = 16;
  v4 = 0;
  v75 = 16;
  v76 = 16;
  if ( v1 )
  {
    while ( 1 )
    {
      if ( (Microsoft_Windows_DirectCompositionEnableBits & 4) != 0 )
      {
        v22 = *(_QWORD *)(v1 + 24);
        v60 = (__int128 *)v1;
        v62 = 32;
        v80 = 4;
        v23 = *(_QWORD *)(v22 + 24);
        v82 = 4;
        v84 = 8;
        v65 = *(_DWORD *)(v23 + 168);
        v79 = &v65;
        v81 = &v62;
        v83 = &v60;
        v59 = &v78;
        McGenEventWrite_EventWriteTransfer(v23, &DCOMPEVENT_UPDATE_TOKEN_Start);
      }
      v4 = DirectComposition::CBitmapInfoFront::CommitUpdate((DirectComposition::CBitmapInfoFront *)v1);
      if ( v4 < 0 )
        goto LABEL_45;
      v25 = *(_QWORD *)(v1 + 16);
      v26 = *(_QWORD *)(v25 + 64);
      v27 = *(_DWORD *)(v25 + 72);
      v28 = *(_DWORD *)(v25 + 76);
      v29 = *(_DWORD *)(v25 + 88);
      LODWORD(hObject) = *(_DWORD *)(v25 + 80);
      v30 = *(_DWORD *)(v25 + 84);
      v31 = *(_QWORD *)(v26 + 144);
      LODWORD(v60) = v30;
      v62 = v27;
      v64[0] = v28;
      v32 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v31 + 128) + 24LL) + 388LL);
      if ( v32 != *(_DWORD *)(v26 + 192) )
      {
        v33 = (unsigned int)(HIDWORD(v71) + 1);
        if ( (unsigned int)v33 < HIDWORD(v71) )
        {
          v2 = -2147024362;
          DoStackCaptureDirect(-2147024362, 0xB7u);
        }
        else
        {
          v34 = (__int64 *)(v26 + 16);
          if ( (unsigned int)v33 > (unsigned int)v71 )
          {
            v51 = DynArrayImpl<0>::AddMultipleAndSet(&v68, 8, v33, v34, v59);
            v2 = v51;
            if ( v51 < 0 )
            {
              DoStackCaptureDirect(v51, 0xC2u);
              v4 = v2;
              goto LABEL_44;
            }
          }
          else
          {
            v24 = *v34;
            *((_QWORD *)v68 + HIDWORD(v71)) = *v34;
            HIDWORD(v71) = v33;
          }
          *(_DWORD *)(v26 + 192) = v32;
        }
        v4 = v2;
        if ( v2 < 0 )
          goto LABEL_44;
        v27 = v62;
        v28 = v64[0];
      }
      *(_QWORD *)&v66 = *(_QWORD *)(v26 + 24);
      *((_QWORD *)&v66 + 1) = __PAIR64__(v28, v27);
      LODWORD(v67) = v27 + (_DWORD)hObject + ((v29 >> 1) & 1) + (v29 & 1);
      HIDWORD(v67) = v28 + (_DWORD)v60 + ((v29 >> 3) & 1) + ((v29 >> 2) & 1);
      v35 = HIDWORD(v76) + 1;
      if ( (unsigned int)(HIDWORD(v76) + 1) < HIDWORD(v76) )
      {
        v4 = -2147024362;
        v38 = 183;
        v39 = -2147024362;
LABEL_51:
        DoStackCaptureDirect(v39, v38);
        goto LABEL_44;
      }
      if ( v35 > (unsigned int)v76 )
      {
        v60 = &v66;
        v49 = DynArrayImpl<0>::Grow((unsigned int)&lpMem, 24, 1, 0, (__int64)&v60);
        v4 = v49;
        if ( v49 >= 0 )
        {
          v50 = v60;
          v24 = (__int64)lpMem + (unsigned int)(24 * HIDWORD(v76));
          *(_OWORD *)v24 = *v60;
          *(_QWORD *)(v24 + 16) = *((_QWORD *)v50 + 2);
          ++HIDWORD(v76);
          goto LABEL_44;
        }
        v38 = 194;
        v39 = v49;
        goto LABEL_51;
      }
      v24 = 3LL * HIDWORD(v76);
      v4 = 0;
      v36 = lpMem;
      *(_OWORD *)((char *)lpMem + 8 * v24) = v66;
      v36[v24 + 2] = v67;
      HIDWORD(v76) = v35;
LABEL_44:
      v2 = 0;
LABEL_45:
      *(_BYTE *)(v1 + 112) &= ~2u;
      if ( (Microsoft_Windows_DirectCompositionEnableBits & 4) != 0 )
      {
        v59 = &v85;
        McGenEventWrite_EventWriteTransfer(v24, &DCOMPEVENT_UPDATE_TOKEN_Stop);
      }
      if ( v4 >= 0 )
      {
        v37 = *((_QWORD *)this + 41);
        v1 = *(_QWORD *)(v37 + 104);
        *(_QWORD *)(v37 + 104) = 0;
        *((_QWORD *)this + 41) = v1;
        if ( v1 )
          continue;
      }
      break;
    }
  }
  for ( i = *((_QWORD *)this + 42); i; *((_QWORD *)this + 42) = i )
  {
    DirectComposition::CYCbCrBitmapInfo::OnDeviceCommit(*(_QWORD *)(i + 48), &v68, &lpMem);
    DirectComposition::CYCbCrBitmapInfo::OnDeviceCommit(*(_QWORD *)(i + 56), &v68, &lpMem);
    *(_BYTE *)(i + 72) = 0;
    v58 = *((_QWORD *)this + 42);
    i = *(_QWORD *)(v58 + 64);
    *(_QWORD *)(v58 + 64) = 0;
  }
  if ( v4 >= 0 )
  {
    v4 = 0;
    while ( 1 )
    {
      v6 = *((_QWORD *)this + 43);
      if ( !v6 )
        break;
      v7 = *(_QWORD *)(*(_QWORD *)(v6 + 144) + 128LL);
      v8 = (__int128 *)(v7 + 8);
      if ( !v7 )
        v8 = 0;
      v60 = v8;
      v9 = *((_QWORD *)v8 + 2);
      v10 = *(_QWORD *)(v9 + 104);
      if ( v10 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 48LL))(v10);
        v8 = v60;
      }
      if ( *(_DWORD *)(v9 + 676) )
        ModuleFailFastForHRESULT(2291664897LL, retaddr);
      DirectComposition::MultithreadDeviceLock::Enter((const struct DirectComposition::CDxDevice *)v8);
      v61 = 0;
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)v60 + 11) + 1048LL))(
        *((_QWORD *)v60 + 11),
        *((_QWORD *)v60 + 10),
        &v61);
      DirectComposition::CAtlasSurfacePool::RemoveGuardRect((DirectComposition::CAtlasSurfacePool *)v6);
      v4 = DirectComposition::CDxDevice::ExecuteGutterExtensions(
             (DirectComposition::CDxDevice *)(*(_QWORD *)(*(_QWORD *)(v6 + 144) + 128LL) + 8LL),
             *(_DWORD *)(v6 + 152),
             *(_DWORD *)(v6 + 156),
             *(_DWORD *)(v6 + 160));
      if ( v4 >= 0 )
        DynArray<unsigned int,0>::Reset(v6 + 208);
      DirectComposition::CAtlasSurfacePool::RestoreGuardRect((DirectComposition::CAtlasSurfacePool *)v6);
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)v60 + 11) + 1048LL))(
        *((_QWORD *)v60 + 11),
        v61,
        0);
      if ( v61 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      v17 = v60;
      v18 = *((_QWORD *)v60 + 4);
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 32LL))(v18);
      v19 = *((_QWORD *)v17 + 5);
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 40LL))(v19);
      if ( v4 < 0 )
        goto LABEL_13;
      v20 = *((_QWORD *)this + 43);
      v21 = *(_QWORD *)(v20 + 240);
      *(_QWORD *)(v20 + 240) = 0;
      *((_QWORD *)this + 43) = v21;
    }
    v11 = HIDWORD(v71);
    if ( HIDWORD(v71) )
    {
      v40 = *((_QWORD *)this + 3);
      v4 = 0;
      v41 = lpMem;
      v42 = HIDWORD(v76);
      v43 = v68;
      v44 = (_QWORD *)(v40 + 632);
      hObject = 0;
      *(_QWORD *)v64 = 0;
      if ( !*(_QWORD *)(v40 + 632) )
        v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)(v40 + 168) + 72LL))(
               *(_QWORD *)(v40 + 168),
               v44);
      *(_QWORD *)v64 = *v44;
      if ( v4 >= 0 )
      {
        v60 = (__int128 *)*((_QWORD *)this + 15);
        v45 = NtTokenManagerCreateCompositionTokenHandle(v41, v42, v11, &v60);
        v4 = DirectComposition::CDevice::HRESULTFromNTSTATUS(v45);
        if ( v4 >= 0 )
        {
          v46 = (DirectComposition::CSurfaceFactory *)((char *)this + 8);
          v47 = hObject;
          v48 = DirectComposition::CDevice::CheckClientDrawNotInProgress(*((DirectComposition::CDevice **)this + 3));
          if ( v48 < 0 )
            ModuleFailFastForHRESULT((unsigned int)v48, retaddr);
          DirectComposition::MultithreadDeviceLock::Enter((DirectComposition::CSurfaceFactory *)((char *)this + 8));
          v52 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int128 **))*((_QWORD *)this + 4);
          v60 = 0;
          v53 = **v52;
          Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v60);
          v54 = v53(v52, &GUID_26c5dc23_e49c_4b0a_8f79_e7b1ac804d32, &v60);
          v4 = v54;
          if ( v54 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x59,
              (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\dll\\kerneltokenfactory.cpp",
              (const char *)(unsigned int)v54,
              (int)v64);
            v57 = v60;
            if ( v60 )
            {
              v60 = 0;
              (*(void (__fastcall **)(__int128 *))(*(_QWORD *)v57 + 16LL))(v57);
            }
          }
          else
          {
            v55 = (*(__int64 (__fastcall **)(__int128 *, HANDLE, LPVOID, _QWORD))(*(_QWORD *)v60 + 104LL))(
                    v60,
                    v47,
                    v43,
                    v11);
            v4 = v55;
            if ( v55 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5D,
                (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\dll\\kerneltokenfactory.cpp",
                (const char *)(unsigned int)v55,
                (int)v64);
              Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v60);
            }
            else
            {
              v56 = v60;
              if ( v60 )
              {
                v60 = 0;
                (*(void (__fastcall **)(__int128 *))(*(_QWORD *)v56 + 16LL))(v56);
              }
              v4 = 0;
            }
          }
          DirectComposition::MultithreadDeviceLock::Leave(v46);
          CloseHandle(hObject);
        }
      }
    }
  }
LABEL_13:
  v12 = lpMem;
  if ( lpMem != v74 )
  {
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
    }
    lpMem = 0;
  }
  v14 = v68;
  if ( v68 != v69 && v68 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v14);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800249f0  push    rbp
0x1800249f2  push    rbx
0x1800249f3  push    rsi
0x1800249f4  push    rdi
0x1800249f5  push    r12
0x1800249f7  push    r13
0x1800249f9  push    r14
0x1800249fb  push    r15
0x1800249fd  lea     rbp, [rsp-238h]
0x180024a05  sub     rsp, 338h
0x180024a0c  mov     rax, cs:__security_cookie
0x180024a13  xor     rax, rsp
0x180024a16  mov     [rbp+270h+var_50], rax
0x180024a1d  mov     rbx, [rcx+148h]
0x180024a24  lea     rax, [rbp+270h+var_2C0]
0x180024a28  mov     [rbp+270h+var_2E0], rax
0x180024a2c  xor     r15d, r15d
0x180024a2f  mov     [rbp+270h+var_2D0], 10h
0x180024a36  lea     rax, [rbp+270h+var_2C0]
0x180024a3a  mov     [rbp+270h+var_2D8], rax
0x180024a3e  lea     rax, [rbp+270h+var_220]
0x180024a42  mov     [rbp+270h+lpMem], rax
0x180024a46  lea     rax, [rbp+270h+var_220]
0x180024a4a  mov     [rbp+270h+var_238], rax
0x180024a4e  mov     rdi, rcx
0x180024a51  mov     [rbp+270h+var_2CC], 10h
0x180024a59  mov     esi, r15d
0x180024a5c  mov     [rbp+270h+var_230], 10h
0x180024a63  mov     [rbp+270h+var_22C], 10h
0x180024a6b  test    rbx, rbx
0x180024a6e  jnz     loc_180024CA0
0x180024a74  mov     rbx, [rdi+150h]
0x180024a7b  test    rbx, rbx
0x180024a7e  jnz     loc_180025118
0x180024a84  test    esi, esi
0x180024a86  js      short loc_180024B03
0x180024a88  mov     esi, r15d
0x180024a8b  mov     rbx, [rdi+158h]
0x180024a92  test    rbx, rbx
0x180024a95  jz      short loc_180024AF2
0x180024a97  mov     rax, [rbx+90h]
0x180024a9e  mov     rcx, [rax+80h]
0x180024aa5  test    rcx, rcx
0x180024aa8  lea     rdx, [rcx+8]
0x180024aac  cmovz   rdx, r15
0x180024ab0  mov     [rsp+370h+var_330], rdx
0x180024ab5  mov     rsi, [rdx+10h]
0x180024ab9  mov     rcx, [rsi+68h]
0x180024abd  test    rcx, rcx
0x180024ac0  jz      short loc_180024AD3
0x180024ac2  mov     rax, [rcx]
0x180024ac5  mov     rax, [rax+30h]
0x180024ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ace  mov     rdx, [rsp+370h+var_330]
0x180024ad3  cmp     dword ptr [rsi+2A4h], 0
0x180024ada  jz      loc_180024B76
0x180024ae0  mov     rdx, [rbp+278h]
0x180024ae7  mov     ecx, 88980801h
0x180024aec  call    ModuleFailFastForHRESULT
0x180024af2  test    esi, esi
0x180024af4  js      short loc_180024B03
0x180024af6  mov     r14d, dword ptr [rbp+270h+var_2CC+4]
0x180024afa  test    r14d, r14d
0x180024afd  jnz     loc_180024EE2
0x180024b03  mov     rbx, [rbp+270h+lpMem]
0x180024b07  cmp     rbx, [rbp+270h+var_238]
0x180024b0b  jz      short loc_180024B2E
0x180024b0d  test    rbx, rbx
0x180024b10  jz      short loc_180024B26
0x180024b12  call    cs:__imp_GetProcessHeap
0x180024b18  mov     r8, rbx; lpMem
0x180024b1b  xor     edx, edx; dwFlags
0x180024b1d  mov     rcx, rax; hHeap
0x180024b20  call    cs:__imp_HeapFree
0x180024b26  mov     [rbp+270h+lpMem], 0
0x180024b2e  mov     rbx, [rbp+270h+var_2E0]
0x180024b32  cmp     rbx, [rbp+270h+var_2D8]
0x180024b36  jz      short loc_180024B51
0x180024b38  test    rbx, rbx
0x180024b3b  jz      short loc_180024B51
0x180024b3d  call    cs:__imp_GetProcessHeap
0x180024b43  mov     r8, rbx; lpMem
0x180024b46  xor     edx, edx; dwFlags
0x180024b48  mov     rcx, rax; hHeap
0x180024b4b  call    cs:__imp_HeapFree
0x180024b51  mov     eax, esi
0x180024b53  mov     rcx, [rbp+270h+var_50]
0x180024b5a  xor     rcx, rsp; StackCookie
0x180024b5d  call    __security_check_cookie
0x180024b62  add     rsp, 338h
0x180024b69  pop     r15
0x180024b6b  pop     r14
0x180024b6d  pop     r13
0x180024b6f  pop     r12
0x180024b71  pop     rdi
0x180024b72  pop     rsi
0x180024b73  pop     rbx
0x180024b74  pop     rbp
0x180024b75  retn
0x180024b76  mov     rcx, rdx; struct DirectComposition::CDxDevice *
0x180024b79  call    ?Enter@MultithreadDeviceLock@DirectComposition@@SAXPEBVCDxDevice@2@@Z; DirectComposition::MultithreadDeviceLock::Enter(DirectComposition::CDxDevice const *)
0x180024b7e  mov     rdx, [rsp+370h+var_330]
0x180024b83  lea     r8, [rsp+370h+var_328]
0x180024b88  mov     [rsp+370h+var_328], r15
0x180024b8d  mov     rcx, [rdx+58h]
0x180024b91  mov     rdx, [rdx+50h]
0x180024b95  mov     rax, [rcx]
0x180024b98  mov     rax, [rax+418h]
0x180024b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ba4  mov     rcx, rbx; this
0x180024ba7  call    ?RemoveGuardRect@CAtlasSurfacePool@DirectComposition@@QEAAXXZ; DirectComposition::CAtlasSurfacePool::RemoveGuardRect(void)
0x180024bac  mov     rax, [rbx+90h]
0x180024bb3  lea     rdx, [rbx+0D0h]
0x180024bba  mov     r9, [rbx+30h]
0x180024bbe  mov     r8, [rbx+28h]
0x180024bc2  mov     rcx, [rax+80h]
0x180024bc9  mov     eax, [rbx+0A0h]
0x180024bcf  add     rcx, 8; this
0x180024bd3  mov     [rsp+370h+var_340], eax; int
0x180024bd7  mov     eax, [rbx+9Ch]
0x180024bdd  mov     [rsp+370h+var_348], eax; unsigned int
0x180024be1  mov     eax, [rbx+98h]
0x180024be7  mov     [rsp+370h+var_350], eax; unsigned int
0x180024beb  call    ?ExecuteGutterExtensions@CDxDevice@DirectComposition@@QEAAJAEBV?$DynArray@UGutterExtension@DirectComposition@@$0A@@@PEAUID3D11ShaderResourceView@@PEAUID3D11RenderTargetView@@IIW4DXGI_FORMAT@@@Z; DirectComposition::CDxDevice::ExecuteGutterExtensions(DynArray<DirectComposition::GutterExtension,0> const &,ID3D11ShaderResourceView *,ID3D11RenderTargetView *,uint,uint,DXGI_FORMAT)
0x180024bf0  mov     esi, eax
0x180024bf2  test    eax, eax
0x180024bf4  js      short loc_180024C02
0x180024bf6  lea     rcx, [rbx+0D0h]
0x180024bfd  call    ?Reset@?$DynArray@I$0A@@@QEAAXH@Z; DynArray<uint,0>::Reset(int)
0x180024c02  mov     rcx, rbx; this
0x180024c05  call    ?RestoreGuardRect@CAtlasSurfacePool@DirectComposition@@QEAAXXZ; DirectComposition::CAtlasSurfacePool::RestoreGuardRect(void)
0x180024c0a  mov     rax, [rsp+370h+var_330]
0x180024c0f  xor     r8d, r8d
0x180024c12  mov     rdx, [rsp+370h+var_328]
0x180024c17  mov     rcx, [rax+58h]
0x180024c1b  mov     rax, [rcx]
0x180024c1e  mov     rax, [rax+418h]
0x180024c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c2a  mov     rcx, [rsp+370h+var_328]
0x180024c2f  test    rcx, rcx
0x180024c32  jz      short loc_180024C40
0x180024c34  mov     rax, [rcx]
0x180024c37  mov     rax, [rax+10h]
0x180024c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c40  mov     rbx, [rsp+370h+var_330]
0x180024c45  mov     rcx, [rbx+20h]
0x180024c49  test    rcx, rcx
0x180024c4c  jz      short loc_180024C5A
0x180024c4e  mov     rax, [rcx]
0x180024c51  mov     rax, [rax+20h]
0x180024c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c5a  mov     rcx, [rbx+28h]
0x180024c5e  test    rcx, rcx
0x180024c61  jz      short loc_180024C6F
0x180024c63  mov     rax, [rcx]
0x180024c66  mov     rax, [rax+28h]
0x180024c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c6f  test    esi, esi
0x180024c71  js      loc_180024B03
0x180024c77  mov     rcx, [rdi+158h]
0x180024c7e  mov     rax, [rcx+0F0h]
0x180024c85  mov     [rcx+0F0h], r15
0x180024c8c  mov     [rdi+158h], rax
0x180024c93  jmp     loc_180024A8B
0x180024ca0  test    byte ptr cs:Microsoft_Windows_DirectCompositionEnableBits, 4
0x180024ca7  jz      loc_180024D2F
0x180024cad  mov     rax, [rbx+18h]
0x180024cb1  lea     rdx, DCOMPEVENT_UPDATE_TOKEN_Start
0x180024cb8  mov     [rsp+370h+var_330], rbx
0x180024cbd  mov     r9d, 4
0x180024cc3  mov     [rsp+370h+var_320], 20h ; ' '
0x180024ccb  mov     [rbp+270h+var_88], 4
0x180024cd6  mov     rcx, [rax+18h]
0x180024cda  mov     [rbp+270h+var_78], 4
0x180024ce5  mov     [rbp+270h+var_68], 8
0x180024cf0  mov     eax, [rcx+0A8h]
0x180024cf6  mov     [rsp+370h+var_308], eax
0x180024cfa  lea     rax, [rsp+370h+var_308]
0x180024cff  mov     [rbp+270h+var_90], rax
0x180024d06  lea     rax, [rsp+370h+var_320]
0x180024d0b  mov     [rbp+270h+var_80], rax
0x180024d12  lea     rax, [rsp+370h+var_330]
0x180024d17  mov     [rbp+270h+var_70], rax
0x180024d1e  lea     rax, [rbp+270h+var_A0]
0x180024d25  mov     qword ptr [rsp+370h+var_350], rax
0x180024d2a  call    McGenEventWrite_EventWriteTransfer
0x180024d2f  mov     rcx, rbx; this
0x180024d32  call    ?CommitUpdate@CBitmapInfoFront@DirectComposition@@QEAAJXZ; DirectComposition::CBitmapInfoFront::CommitUpdate(void)
0x180024d37  mov     esi, eax
0x180024d39  test    eax, eax
0x180024d3b  js      loc_180024E61
0x180024d41  mov     rax, [rbx+10h]
0x180024d45  mov     ecx, [rax+50h]
0x180024d48  mov     r14, [rax+40h]
0x180024d4c  mov     edx, [rax+48h]
0x180024d4f  mov     r8d, [rax+4Ch]
0x180024d53  mov     r12d, [rax+58h]
0x180024d57  mov     dword ptr [rsp+370h+hObject], ecx
0x180024d5b  mov     ecx, [rax+54h]
0x180024d5e  mov     rax, [r14+90h]
0x180024d65  mov     dword ptr [rsp+370h+var_330], ecx
0x180024d69  mov     [rsp+370h+var_320], edx
0x180024d6d  mov     [rsp+370h+var_310], r8d
0x180024d72  mov     rcx, [rax+80h]
0x180024d79  mov     rax, [rcx+18h]
0x180024d7d  mov     r13d, [rax+184h]
0x180024d84  cmp     r13d, [r14+0C0h]
0x180024d8b  jz      short loc_180024DDB
0x180024d8d  mov     eax, dword ptr [rbp+270h+var_2CC+4]
0x180024d90  lea     r8d, [rax+1]
0x180024d94  cmp     r8d, eax
0x180024d97  jb      loc_180024ECB
0x180024d9d  lea     r9, [r14+10h]
0x180024da1  cmp     r8d, dword ptr [rbp+270h+var_2CC]
0x180024da5  ja      loc_180025004
0x180024dab  mov     rcx, [r9]
0x180024dae  mov     edx, eax
0x180024db0  mov     rax, [rbp+270h+var_2E0]
0x180024db4  mov     [rax+rdx*8], rcx
0x180024db8  mov     dword ptr [rbp+270h+var_2CC+4], r8d
0x180024dbc  mov     [r14+0C0h], r13d
0x180024dc3  mov     esi, r15d
0x180024dc6  test    r15d, r15d
0x180024dc9  js      loc_180024E5E
0x180024dcf  mov     edx, [rsp+370h+var_320]
0x180024dd3  xor     r15d, r15d
0x180024dd6  mov     r8d, [rsp+370h+var_310]
0x180024ddb  mov     rax, [r14+18h]
0x180024ddf  mov     ecx, r12d
0x180024de2  mov     qword ptr [rsp+370h+var_300], rax
0x180024de7  and     ecx, 1
0x180024dea  mov     eax, r12d
0x180024ded  mov     dword ptr [rsp+370h+var_300+8], edx
0x180024df1  shr     eax, 1
0x180024df3  and     eax, 1
0x180024df6  mov     dword ptr [rsp+370h+var_300+0Ch], r8d
0x180024dfb  add     eax, dword ptr [rsp+370h+hObject]
0x180024dff  add     ecx, eax
0x180024e01  mov     eax, r12d
0x180024e04  shr     eax, 3
0x180024e07  add     ecx, edx
0x180024e09  shr     r12d, 2
0x180024e0d  and     eax, 1
0x180024e10  add     eax, dword ptr [rsp+370h+var_330]
0x180024e14  and     r12d, 1
0x180024e18  add     r12d, eax
0x180024e1b  mov     dword ptr [rbp+270h+var_2F0], ecx
0x180024e1e  mov     eax, dword ptr [rbp+270h+var_22C+4]
0x180024e21  add     r12d, r8d
0x180024e24  mov     dword ptr [rbp+270h+var_2F0+4], r12d
0x180024e28  lea     edx, [rax+1]
0x180024e2b  cmp     edx, eax
0x180024e2d  jb      loc_180024EB8
0x180024e33  cmp     edx, dword ptr [rbp+270h+var_22C]
0x180024e36  ja      loc_180024FA5
0x180024e3c  movups  xmm0, [rsp+370h+var_300]
0x180024e41  lea     rcx, [rax+rax*2]
0x180024e45  mov     esi, r15d
0x180024e48  mov     rax, [rbp+270h+lpMem]
0x180024e4c  movups  xmmword ptr [rax+rcx*8], xmm0
0x180024e50  movsd   xmm1, [rbp+270h+var_2F0]
0x180024e55  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x180024e5b  mov     dword ptr [rbp+270h+var_22C+4], edx
0x180024e5e  xor     r15d, r15d
0x180024e61  and     byte ptr [rbx+70h], 0FDh
0x180024e65  test    byte ptr cs:Microsoft_Windows_DirectCompositionEnableBits, 4
0x180024e6c  jz      short loc_180024E8C
0x180024e6e  lea     rax, [rbp+270h+var_60]
0x180024e75  mov     r9d, 1
0x180024e7b  lea     rdx, DCOMPEVENT_UPDATE_TOKEN_Stop
0x180024e82  mov     qword ptr [rsp+370h+var_350], rax
0x180024e87  call    McGenEventWrite_EventWriteTransfer
0x180024e8c  test    esi, esi
0x180024e8e  js      loc_180024A74
0x180024e94  mov     rax, [rdi+148h]
0x180024e9b  mov     rbx, [rax+68h]
0x180024e9f  mov     [rax+68h], r15
0x180024ea3  mov     [rdi+148h], rbx
0x180024eaa  test    rbx, rbx
0x180024ead  jnz     loc_180024CA0
0x180024eb3  jmp     loc_180024A74
0x180024eb8  mov     esi, 80070216h
0x180024ebd  mov     edx, 0B7h; unsigned int
0x180024ec2  mov     ecx, esi; int
0x180024ec4  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180024ec9  jmp     short loc_180024E5E
0x180024ecb  mov     ecx, 80070216h; int
0x180024ed0  mov     edx, 0B7h; unsigned int
0x180024ed5  mov     r15d, ecx
0x180024ed8  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180024edd  jmp     loc_180024DC3
0x180024ee2  mov     rcx, [rdi+18h]
0x180024ee6  xor     esi, esi
0x180024ee8  mov     r15, [rbp+270h+lpMem]
0x180024eec  mov     r12d, dword ptr [rbp+270h+var_22C+4]
0x180024ef0  mov     r13, [rbp+270h+var_2E0]
0x180024ef4  lea     rbx, [rcx+278h]
0x180024efb  mov     [rsp+370h+hObject], 0
0x180024f04  mov     qword ptr [rsp+370h+var_310], 0
0x180024f0d  cmp     [rbx], rsi
  ... truncated ...
```
