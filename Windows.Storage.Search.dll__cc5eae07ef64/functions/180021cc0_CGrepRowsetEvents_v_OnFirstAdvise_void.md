# CGrepRowsetEvents::v_OnFirstAdvise(void)

- ea: `0x180021cc0`
- end: `0x1800220a8`
- name: `?v_OnFirstAdvise@CGrepRowsetEvents@@MEAAJXZ`
- size: `1000`
- prototype: `__int64 __fastcall(IUnknown *punkSite)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180014498`
- `0x180021a34`
- `0x180021b70`
- `0x180021bf8`
- `0x180021cc0`
- `0x180022cf4`
- `0x18003a69c`
- `0x180069e7c`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_SetSite` at `0x180022047`
- `SHCORE!IUnknown_SetSite` at `0x180022047`
- `Windows.Storage!SHGetIDListFromObject` at `0x180021f19`
- `Windows.Storage!SHGetIDListFromObject` at `0x180021f19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021f27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022023`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002209a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021f27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022023`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002209a`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CGrepRowsetEvents::v_OnFirstAdvise(IUnknown *punkSite)
{
  int KeysInCondition; // edi
  struct IUnknownVtbl *lpVtbl; // rdi
  __int64 (__fastcall *v4)(struct IUnknownVtbl *, __int64, GUID *, __int64 *); // rbx
  __int64 *v5; // rax
  unsigned __int64 v6; // rbx
  char v7; // r14
  const struct CGrepRowsetEvents::SCOPE_REGISTRATION *v8; // r15
  unsigned __int64 v9; // rsi
  unsigned int v10; // r12d
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, GUID *, __int64 *); // rbx
  __int64 v13; // rcx
  __int64 v14; // rcx
  struct IPropertyKeyStore *v15; // rcx
  IUnknown *v17; // rcx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, GUID *, __int64 *); // rbx
  __int64 *v20; // rax
  CGrepRowsetEvents *v21; // rcx
  IUnknown *v22; // rcx
  const struct _GUID *v23; // rdx
  __int64 v24; // r12
  LPITEMIDLIST v25; // rbx
  void *v26; // rcx
  IUnknown *v27; // rcx
  __int64 v28; // [rsp+30h] [rbp-49h] BYREF
  int v29; // [rsp+38h] [rbp-41h] BYREF
  IUnknown *punk; // [rsp+40h] [rbp-39h] BYREF
  __int64 v31; // [rsp+48h] [rbp-31h] BYREF
  struct IPropertyKeyStore *v32; // [rsp+50h] [rbp-29h] BYREF
  LPITEMIDLIST ppidl; // [rsp+58h] [rbp-21h] BYREF
  bool v34; // [rsp+60h] [rbp-19h]
  const struct CGrepRowsetEvents::SCOPE_REGISTRATION *v35; // [rsp+68h] [rbp-11h] BYREF
  __int64 v36; // [rsp+70h] [rbp-9h]
  __int64 v37; // [rsp+78h] [rbp-1h]
  __int64 v38; // [rsp+80h] [rbp+7h]
  __int64 v39; // [rsp+88h] [rbp+Fh]
  unsigned int v40; // [rsp+E0h] [rbp+67h] BYREF
  IUnknown *v41; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int v42; // [rsp+F0h] [rbp+77h] BYREF
  const struct CGrepRowsetEvents::SCOPE_REGISTRATION *v43; // [rsp+F8h] [rbp+7Fh] BYREF

  KeysInCondition = 0;
  if ( punkSite[10].lpVtbl )
  {
    v32 = 0;
    if ( !punkSite[11].lpVtbl
      || (Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32),
          KeysInCondition = GetKeysInCondition((struct ICondition *)punkSite[11].lpVtbl, v23, (void **)&v32),
          KeysInCondition >= 0) )
    {
      v31 = 0;
      lpVtbl = punkSite[10].lpVtbl;
      v4 = (__int64 (__fastcall *)(struct IUnknownVtbl *, __int64, GUID *, __int64 *))*((_QWORD *)lpVtbl->QueryInterface
                                                                                      + 8);
      v5 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(&v31);
      KeysInCondition = v4(lpVtbl, 4096, &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9, v5);
      v6 = 0;
      if ( KeysInCondition >= 0 )
      {
        v7 = 1;
        LOBYTE(v40) = 1;
        v8 = 0;
        v35 = 0;
        v9 = 0;
        v36 = 0;
        v37 = 0;
        v38 = 0;
        v42 = 0;
        KeysInCondition = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v31 + 24LL))(v31, &v42);
        v10 = 0;
        LODWORD(v41) = 0;
        if ( KeysInCondition >= 0 )
        {
          while ( v10 < v42 )
          {
            if ( v7 )
            {
              v28 = 0;
              v11 = v31;
              v12 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v31 + 32LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
              KeysInCondition = v12(v11, v10, &GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0, &v28);
              v6 = 0;
              if ( KeysInCondition >= 0 )
              {
                LODWORD(v43) = 0;
                KeysInCondition = (*(__int64 (__fastcall **)(__int64, const struct CGrepRowsetEvents::SCOPE_REGISTRATION **))(*(_QWORD *)v28 + 64LL))(
                                    v28,
                                    &v43);
                if ( KeysInCondition >= 0 )
                {
                  if ( (char)v43 >= 0 )
                  {
                    v7 = 0;
                    LOBYTE(v40) = 0;
                  }
                  else
                  {
                    punk = 0;
                    v18 = v28;
                    v19 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v28 + 120LL);
                    v20 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>((__int64 *)&punk);
                    KeysInCondition = v19(v18, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v20);
                    v6 = 0;
                    if ( KeysInCondition >= 0 )
                    {
                      if ( !v32
                        || (KeysInCondition = CGrepRowsetEvents::_AreAllPropertiesFastForItem(
                                                v21,
                                                v32,
                                                (struct IShellItem *)punk,
                                                (bool *)&v40),
                            v7 = v40,
                            KeysInCondition >= 0) )
                      {
                        if ( v7 )
                        {
                          ppidl = 0;
                          v34 = 0;
                          v39 = 0;
                          KeysInCondition = SHGetIDListFromObject(punk, &ppidl);
                          if ( KeysInCondition >= 0 )
                          {
                            v29 = 0;
                            KeysInCondition = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 48LL))(
                                                v28,
                                                &v29);
                            if ( KeysInCondition >= 0 )
                            {
                              v34 = v29 == 2;
                              KeysInCondition = 0;
                              if ( v9 != v38
                                || (KeysInCondition = CTSimpleArray<CConnectionPointBase<IRowsetEvents>::CConnectData,4294967294,CTPolicyCoTaskMem<CConnectionPointBase<IRowsetEvents>::CConnectData>,CSimpleArrayStandardCompareHelper<CConnectionPointBase<IRowsetEvents>::CConnectData>,CSimpleArrayStandardMergeHelper<CConnectionPointBase<IRowsetEvents>::CConnectData>>::_EnsureCapacity(
                                                        &v35,
                                                        v9 + 1),
                                    v9 = v36,
                                    v8 = v35,
                                    KeysInCondition >= 0) )
                              {
                                v36 = ++v9;
                                v24 = (__int64)v8 + 16 * v9 - 16;
                                if ( v24 )
                                {
                                  *(_QWORD *)v24 = 0;
                                  v25 = ppidl;
                                  ppidl = 0;
                                  v26 = *(void **)v24;
                                  *(_QWORD *)v24 = 0;
                                  CoTaskMemFree(v26);
                                  *(_QWORD *)v24 = v25;
                                  *(_BYTE *)(v24 + 8) = v34;
                                  v6 = 0;
                                }
                                v10 = (unsigned int)v41;
                              }
                            }
                          }
                          CoTaskMemFree(0);
                          CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppidl);
                        }
                      }
                    }
                    v22 = punk;
                    if ( punk )
                    {
                      punk = 0;
                      ((void (__fastcall *)(IUnknown *))v22->lpVtbl->Release)(v22);
                    }
                  }
                }
              }
              v13 = v28;
              if ( v28 )
              {
                v28 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
              }
              LODWORD(v41) = ++v10;
              if ( KeysInCondition >= 0 )
                continue;
            }
            if ( KeysInCondition < 0 )
              goto LABEL_13;
            break;
          }
          if ( v7 )
          {
            v41 = 0;
            v43 = v8;
            v40 = v9;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
            KeysInCondition = Microsoft::WRL::Details::MakeAndInitialize<CGrepRowsetEvents::CNotificationThread,IObjectWithCancelEvent,unsigned int,CGrepRowsetEvents::SCOPE_REGISTRATION *>(
                                &v41,
                                &v40,
                                &v43);
            if ( KeysInCondition >= 0 )
            {
              IUnknown_SetSite(v41, punkSite);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punkSite[12]);
              v27 = v41;
              if ( v41 )
              {
                ((void (__fastcall *)(IUnknown *))v41->lpVtbl->AddRef)(v41);
                v27 = v41;
              }
              punkSite[12].lpVtbl = (struct IUnknownVtbl *)v27;
              KeysInCondition = 0;
            }
            v17 = v41;
            if ( v41 )
            {
              v41 = 0;
              ((void (__fastcall *)(IUnknown *))v17->lpVtbl->Release)(v17);
            }
          }
        }
LABEL_13:
        if ( v8 )
        {
          if ( v9 )
          {
            do
              CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((char *)v8 + 16 * v6++);
            while ( v6 < v9 );
          }
          CoTaskMemFree(v8);
        }
      }
      v14 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
    v15 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(struct IPropertyKeyStore *))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  return (unsigned int)KeysInCondition;
}

```

## disassembly

```asm
0x180021cc0  push    rbp
0x180021cc2  push    rbx
0x180021cc3  push    rsi
0x180021cc4  push    rdi
0x180021cc5  push    r12
0x180021cc7  push    r13
0x180021cc9  push    r14
0x180021ccb  push    r15
0x180021ccd  lea     rbp, [rsp-1Fh]
0x180021cd2  sub     rsp, 98h
0x180021cd9  mov     r13, rcx
0x180021cdc  xor     ebx, ebx
0x180021cde  mov     edi, ebx
0x180021ce0  cmp     [rcx+50h], rbx
0x180021ce4  jz      loc_180021E50
0x180021cea  mov     [rbp+57h+var_80], rbx
0x180021cee  cmp     [rcx+58h], rbx
0x180021cf2  jnz     loc_180021F70
0x180021cf8  mov     [rbp+57h+var_88], rbx
0x180021cfc  mov     rdi, [r13+50h]
0x180021d00  mov     rax, [rdi]
0x180021d03  mov     rbx, [rax+40h]
0x180021d07  lea     rcx, [rbp+57h+var_88]
0x180021d0b  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellItem>>)
0x180021d10  mov     r9, rax
0x180021d13  lea     r8, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x180021d1a  mov     edx, 1000h
0x180021d1f  mov     rcx, rdi
0x180021d22  mov     rax, rbx
0x180021d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d2a  mov     edi, eax
0x180021d2c  xor     ebx, ebx
0x180021d2e  test    eax, eax
0x180021d30  js      loc_180021E1C
0x180021d36  mov     r14b, 1
0x180021d39  mov     byte ptr [rbp+57h+arg_0], r14b
0x180021d3d  mov     r15d, ebx
0x180021d40  mov     [rbp+57h+var_68], rbx
0x180021d44  mov     esi, ebx
0x180021d46  mov     [rbp+57h+var_60], rbx
0x180021d4a  mov     [rbp+57h+var_58], rbx
0x180021d4e  mov     [rbp+57h+var_50], rbx
0x180021d52  mov     [rbp+57h+arg_10], ebx
0x180021d55  mov     rcx, [rbp+57h+var_88]
0x180021d59  mov     rax, [rcx]
0x180021d5c  lea     rdx, [rbp+57h+arg_10]
0x180021d60  mov     rax, [rax+18h]
0x180021d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d69  mov     edi, eax
0x180021d6b  mov     r12d, ebx
0x180021d6e  mov     dword ptr [rbp+57h+arg_8], ebx
0x180021d71  test    eax, eax
0x180021d73  js      loc_180021E13
0x180021d79  cmp     r12d, [rbp+57h+arg_10]
0x180021d7d  jnb     loc_180021E66
0x180021d83  test    r14b, r14b
0x180021d86  jz      loc_180021E0F
0x180021d8c  mov     [rbp+57h+var_A0], rbx
0x180021d90  mov     rdi, [rbp+57h+var_88]
0x180021d94  mov     rax, [rdi]
0x180021d97  mov     rbx, [rax+20h]
0x180021d9b  lea     rcx, [rbp+57h+var_A0]
0x180021d9f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021da4  lea     r9, [rbp+57h+var_A0]
0x180021da8  lea     r8, _GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0
0x180021daf  mov     edx, r12d
0x180021db2  mov     rcx, rdi
0x180021db5  mov     rax, rbx
0x180021db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dbd  mov     edi, eax
0x180021dbf  xor     ebx, ebx
0x180021dc1  test    eax, eax
0x180021dc3  js      short loc_180021DE6
0x180021dc5  mov     dword ptr [rbp+57h+arg_18], ebx
0x180021dc8  mov     rcx, [rbp+57h+var_A0]
0x180021dcc  mov     rax, [rcx]
0x180021dcf  lea     rdx, [rbp+57h+arg_18]
0x180021dd3  mov     rax, [rax+40h]
0x180021dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ddc  mov     edi, eax
0x180021dde  test    eax, eax
0x180021de0  jns     loc_180021EB9
0x180021de6  mov     rcx, [rbp+57h+var_A0]
0x180021dea  test    rcx, rcx
0x180021ded  jz      short loc_180021E00
0x180021def  mov     [rbp+57h+var_A0], rbx
0x180021df3  mov     rax, [rcx]
0x180021df6  mov     rax, [rax+10h]
0x180021dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dff  nop
0x180021e00  inc     r12d
0x180021e03  mov     dword ptr [rbp+57h+arg_8], r12d
0x180021e07  test    edi, edi
0x180021e09  jns     loc_180021D79
0x180021e0f  test    edi, edi
0x180021e11  jns     short loc_180021E66
0x180021e13  test    r15, r15
0x180021e16  jnz     loc_18002207B
0x180021e1c  mov     rcx, [rbp+57h+var_88]
0x180021e20  test    rcx, rcx
0x180021e23  jz      short loc_180021E36
0x180021e25  mov     [rbp+57h+var_88], rbx
0x180021e29  mov     rax, [rcx]
0x180021e2c  mov     rax, [rax+10h]
0x180021e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e35  nop
0x180021e36  mov     rcx, [rbp+57h+var_80]
0x180021e3a  test    rcx, rcx
0x180021e3d  jz      short loc_180021E50
0x180021e3f  mov     [rbp+57h+var_80], rbx
0x180021e43  mov     rax, [rcx]
0x180021e46  mov     rax, [rax+10h]
0x180021e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e4f  nop
0x180021e50  mov     eax, edi
0x180021e52  add     rsp, 98h
0x180021e59  pop     r15
0x180021e5b  pop     r14
0x180021e5d  pop     r13
0x180021e5f  pop     r12
0x180021e61  pop     rdi
0x180021e62  pop     rsi
0x180021e63  pop     rbx
0x180021e64  pop     rbp
0x180021e65  retn
0x180021e66  test    r14b, r14b
0x180021e69  jz      short loc_180021E13
0x180021e6b  mov     [rbp+57h+arg_8], rbx
0x180021e6f  mov     [rbp+57h+arg_18], r15
0x180021e73  mov     [rbp+57h+arg_0], esi
0x180021e76  lea     rcx, [rbp+57h+arg_8]
0x180021e7a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021e7f  lea     r8, [rbp+57h+arg_18]
0x180021e83  lea     rdx, [rbp+57h+arg_0]
0x180021e87  lea     rcx, [rbp+57h+arg_8]
0x180021e8b  call    ??$MakeAndInitialize@VCNotificationThread@CGrepRowsetEvents@@UIObjectWithCancelEvent@@IPEAUSCOPE_REGISTRATION@2@@Details@WRL@Microsoft@@YAJPEAPEAUIObjectWithCancelEvent@@$$QEAI$$QEAPEAUSCOPE_REGISTRATION@CGrepRowsetEvents@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CGrepRowsetEvents::CNotificationThread,IObjectWithCancelEvent,uint,CGrepRowsetEvents::SCOPE_REGISTRATION *>(IObjectWithCancelEvent * *,uint &&,CGrepRowsetEvents::SCOPE_REGISTRATION * &&)
0x180021e90  mov     edi, eax
0x180021e92  test    eax, eax
0x180021e94  jns     loc_180022040
0x180021e9a  mov     rcx, [rbp+57h+arg_8]
0x180021e9e  test    rcx, rcx
0x180021ea1  jz      short loc_180021EB4
0x180021ea3  mov     [rbp+57h+arg_8], rbx
0x180021ea7  mov     rax, [rcx]
0x180021eaa  mov     rax, [rax+10h]
0x180021eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021eb3  nop
0x180021eb4  jmp     loc_180021E13
0x180021eb9  test    byte ptr [rbp+57h+arg_18], 80h
0x180021ebd  jz      loc_180021F95
0x180021ec3  mov     [rbp+57h+punk], rbx
0x180021ec7  mov     rdi, [rbp+57h+var_A0]
0x180021ecb  mov     rax, [rdi]
0x180021ece  mov     rbx, [rax+78h]
0x180021ed2  lea     rcx, [rbp+57h+punk]
0x180021ed6  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellItem>>)
0x180021edb  mov     r8, rax
0x180021ede  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180021ee5  mov     rcx, rdi
0x180021ee8  mov     rax, rbx
0x180021eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ef0  mov     edi, eax
0x180021ef2  xor     ebx, ebx
0x180021ef4  test    eax, eax
0x180021ef6  js      short loc_180021F38
0x180021ef8  mov     rdx, [rbp+57h+var_80]; struct IPropertyKeyStore *
0x180021efc  test    rdx, rdx
0x180021eff  jnz     short loc_180021F57
0x180021f01  test    r14b, r14b
0x180021f04  jz      short loc_180021F38
0x180021f06  mov     [rbp+57h+ppidl], rbx
0x180021f0a  mov     [rbp+57h+var_70], bl
0x180021f0d  mov     [rbp+57h+var_48], rbx
0x180021f11  lea     rdx, [rbp+57h+ppidl]; ppidl
0x180021f15  mov     rcx, [rbp+57h+punk]; punk
0x180021f19  call    cs:__imp_SHGetIDListFromObject
0x180021f1f  mov     edi, eax
0x180021f21  test    eax, eax
0x180021f23  jns     short loc_180021FA0
0x180021f25  xor     ecx, ecx; pv
0x180021f27  call    cs:__imp_CoTaskMemFree
0x180021f2d  nop
0x180021f2e  lea     rcx, [rbp+57h+ppidl]
0x180021f32  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180021f37  nop
0x180021f38  mov     rcx, [rbp+57h+punk]
0x180021f3c  test    rcx, rcx
0x180021f3f  jz      short loc_180021F52
0x180021f41  mov     [rbp+57h+punk], rbx
0x180021f45  mov     rax, [rcx]
0x180021f48  mov     rax, [rax+10h]
0x180021f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f51  nop
0x180021f52  jmp     loc_180021DE6
0x180021f57  lea     r9, [rbp+57h+arg_0]; bool *
0x180021f5b  mov     r8, [rbp+57h+punk]; struct IShellItem *
0x180021f5f  call    ?_AreAllPropertiesFastForItem@CGrepRowsetEvents@@AEAAJPEAUIPropertyKeyStore@@PEAUIShellItem@@PEA_N@Z; CGrepRowsetEvents::_AreAllPropertiesFastForItem(IPropertyKeyStore *,IShellItem *,bool *)
0x180021f64  mov     edi, eax
0x180021f66  mov     r14b, byte ptr [rbp+57h+arg_0]
0x180021f6a  test    eax, eax
0x180021f6c  jns     short loc_180021F01
0x180021f6e  jmp     short loc_180021F38
0x180021f70  lea     rcx, [rbp+57h+var_80]
0x180021f74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021f79  lea     r8, [rbp+57h+var_80]; void **
0x180021f7d  mov     rcx, [r13+58h]; struct ICondition *
0x180021f81  call    ?GetKeysInCondition@@YAJPEAUICondition@@AEBU_GUID@@PEAPEAX@Z; GetKeysInCondition(ICondition *,_GUID const &,void * *)
0x180021f86  mov     edi, eax
0x180021f88  test    eax, eax
0x180021f8a  js      loc_180021E36
0x180021f90  jmp     loc_180021CF8
0x180021f95  mov     r14b, bl
0x180021f98  mov     byte ptr [rbp+57h+arg_0], bl
0x180021f9b  jmp     loc_180021DE6
0x180021fa0  mov     [rbp+57h+var_98], ebx
0x180021fa3  mov     rcx, [rbp+57h+var_A0]
0x180021fa7  mov     rax, [rcx]
0x180021faa  lea     rdx, [rbp+57h+var_98]
0x180021fae  mov     rax, [rax+30h]
0x180021fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fb7  mov     edi, eax
0x180021fb9  test    eax, eax
0x180021fbb  js      loc_180021F25
0x180021fc1  cmp     [rbp+57h+var_98], 2
0x180021fc5  setz    [rbp+57h+var_70]
0x180021fc9  mov     edi, ebx
0x180021fcb  cmp     rsi, [rbp+57h+var_50]
0x180021fcf  jnz     short loc_180021FF0
0x180021fd1  lea     rdx, [rsi+1]
0x180021fd5  lea     rcx, [rbp+57h+var_68]
0x180021fd9  call    ?_EnsureCapacity@?$CTSimpleArray@VCConnectData@?$CConnectionPointBase@UIRowsetEvents@@@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@VCConnectData@?$CConnectionPointBase@UIRowsetEvents@@@@@@V?$CSimpleArrayStandardCompareHelper@VCConnectData@?$CConnectionPointBase@UIRowsetEvents@@@@@@V?$CSimpleArrayStandardMergeHelper@VCConnectData@?$CConnectionPointBase@UIRowsetEvents@@@@@@@@QEAAJ_K0@Z; CTSimpleArray<CConnectionPointBase<IRowsetEvents>::CConnectData,4294967294,CTPolicyCoTaskMem<CConnectionPointBase<IRowsetEvents>::CConnectData>,CSimpleArrayStandardCompareHelper<CConnectionPointBase<IRowsetEvents>::CConnectData>,CSimpleArrayStandardMergeHelper<CConnectionPointBase<IRowsetEvents>::CConnectData>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180021fde  mov     edi, eax
0x180021fe0  mov     rsi, [rbp+57h+var_60]
0x180021fe4  mov     r15, [rbp+57h+var_68]
0x180021fe8  test    eax, eax
0x180021fea  js      loc_180021F25
0x180021ff0  inc     rsi
0x180021ff3  mov     [rbp+57h+var_60], rsi
0x180021ff7  mov     rax, rsi
0x180021ffa  shl     rax, 4
0x180021ffe  lea     r12, [r15-10h]
0x180022002  add     r12, rax
0x180022005  jz      short loc_180022037
0x180022007  mov     [r12], rbx
0x18002200b  mov     rbx, [rbp+57h+ppidl]
0x18002200f  mov     [rbp+57h+ppidl], 0
0x180022017  mov     rcx, [r12]; pv
0x18002201b  mov     qword ptr [r12], 0
0x180022023  call    cs:__imp_CoTaskMemFree
0x180022029  mov     [r12], rbx
0x18002202d  mov     al, [rbp+57h+var_70]
0x180022030  mov     [r12+8], al
0x180022035  xor     ebx, ebx
0x180022037  mov     r12d, dword ptr [rbp+57h+arg_8]
0x18002203b  jmp     loc_180021F25
0x180022040  mov     rdx, r13; punkSite
0x180022043  mov     rcx, [rbp+57h+arg_8]; punk
0x180022047  call    cs:__imp_IUnknown_SetSite
0x18002204d  lea     rcx, [r13+60h]
0x180022051  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022056  nop
0x180022057  mov     rcx, [rbp+57h+arg_8]
0x18002205b  test    rcx, rcx
0x18002205e  jz      short loc_180022070
0x180022060  mov     rax, [rcx]
0x180022063  mov     rax, [rax+8]
0x180022067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002206c  mov     rcx, [rbp+57h+arg_8]
0x180022070  mov     [r13+60h], rcx
0x180022074  mov     edi, ebx
0x180022076  jmp     loc_180021E9A
0x18002207b  test    rsi, rsi
0x18002207e  jz      short loc_180022097
0x180022080  mov     rcx, rbx
0x180022083  shl     rcx, 4
0x180022087  add     rcx, r15
0x18002208a  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18002208f  inc     rbx
0x180022092  cmp     rbx, rsi
0x180022095  jb      short loc_180022080
0x180022097  mov     rcx, r15; pv
0x18002209a  call    cs:__imp_CoTaskMemFree
0x1800220a0  xor     ebx, ebx
0x1800220a2  jmp     loc_180021E1C
```
