# CSimpleAppList::_OnChange(long,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x18026d368`
- end: `0x18026d598`
- name: `?_OnChange@CSimpleAppList@@AEAAXJPEBU_ITEMIDLIST_ABSOLUTE@@0@Z`
- size: `560`
- prototype: `void(CSimpleAppList *__hidden this, int, const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18026ca6c`

## callees

- `0x180009dd0`
- `0x18000aa70`
- `0x1801b837c`
- `0x18026c834`
- `0x18026d368`
- `0x18038c1ec`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026d46a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026d560`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026d46a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026d560`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18026d442`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18026d442`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18026d550`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18026d550`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18026d404`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18026d404`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x18026d522`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x18026d522`
- `api-ms-win-shell-namespace-l1-1-0!ILFindChild` at `0x18026d3a8`
- `api-ms-win-shell-namespace-l1-1-0!ILFindChild` at `0x18026d3a8`

## pseudocode

```c
void __fastcall CSimpleAppList::_OnChange(
        CSimpleAppList *this,
        int a2,
        const ITEMIDLIST *a3,
        const struct _ITEMIDLIST_ABSOLUTE *a4)
{
  LPITEMIDLIST v6; // rax
  const ITEMIDLIST *v7; // r14
  _WORD *v8; // rax
  void **ppvItem; // rax
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, const PROPERTYKEY *, LPVOID *); // rbx
  int v12; // edi
  LPVOID v13; // r15
  unsigned int i; // ebx
  __int64 v15; // rdx
  ITEMIDLIST *v16; // rbx
  __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+40h] [rbp-10h] BYREF
  int v20; // [rsp+88h] [rbp+38h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+48h] BYREF

  ppv = a4;
  if ( a2 == 2 || a2 == 4 )
  {
    v6 = ILFindChild(*(LPITEMIDLIST *)(*((_QWORD *)this + 25) + 24LL), a3);
    v7 = v6;
    if ( v6 )
    {
      if ( !v6->mkid.cb || (v8 = (USHORT *)((char *)&v6->mkid.cb + v6->mkid.cb)) == 0 || !*v8 )
      {
        v17 = 0;
        ppvItem = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(&v17);
        if ( SHCreateItemWithParent(
               *(LPCITEMIDLIST *)(*((_QWORD *)this + 25) + 24LL),
               0,
               v7,
               &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
               ppvItem) < 0 )
        {
LABEL_23:
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v17);
          return;
        }
        ppv = 0;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
        if ( CoCreateInstance(&CLSID_BackgroundTaskCapability, 0, 1u, &GUID_d54e68c2_54cd_48b3_ad9a_3f4a4503ba80, &ppv) < 0 )
        {
LABEL_22:
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
          goto LABEL_23;
        }
        v10 = v17;
        pv = 0;
        v11 = *(int (__fastcall **)(__int64, const PROPERTYKEY *, LPVOID *))(*(_QWORD *)v17 + 136LL);
        CoTaskMemFree(0);
        if ( v11(v10, &PKEY_AppUserModel_ID, &pv) >= 0 )
        {
          v20 = 0;
          if ( a2 == 4 )
          {
            v12 = 1;
            goto LABEL_14;
          }
          if ( (int)IsAppLockScreenCapable(v17, ppv, *(unsigned int *)(*((_QWORD *)this + 25) + 32LL), &v20) >= 0 )
          {
            v12 = 0;
            if ( v20 )
            {
LABEL_14:
              if ( *(_DWORD *)(*((_QWORD *)this + 25) + 48LL) )
              {
                v13 = pv;
                for ( i = 0; ; ++i )
                {
                  v15 = *((_QWORD *)this + 25);
                  if ( i >= *(_DWORD *)(v15 + 48) )
                    break;
                  v19 = 0;
                  if ( (int)CSimpleStringArrayBase<CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::Find(
                              *(_QWORD *)(v15 + 40) + 8 * (5LL * i + 1),
                              v13,
                              &v19) >= 0 )
                    goto LABEL_19;
                }
              }
              else
              {
LABEL_19:
                v16 = ILClone(v7);
                if ( !CAppListHelper::PostMessageW(*((CAppListHelper **)this + 25), v12 + 1034, 0, (__int64)v16) )
                  ILFree(v16);
              }
            }
          }
        }
        CoTaskMemFree(pv);
        goto LABEL_22;
      }
    }
  }
}

```

## disassembly

```asm
0x18026d368  mov     [rsp-28h+arg_0], rbx
0x18026d36d  mov     [rsp-28h+arg_10], rsi
0x18026d372  mov     [rsp-28h+ppv], r9
0x18026d377  push    rbp
0x18026d378  push    rdi
0x18026d379  push    r12
0x18026d37b  push    r14
0x18026d37d  push    r15
0x18026d37f  mov     rbp, rsp
0x18026d382  sub     rsp, 50h
0x18026d386  mov     r15d, edx
0x18026d389  mov     rsi, rcx
0x18026d38c  cmp     edx, 2
0x18026d38f  jz      short loc_18026D39A
0x18026d391  cmp     edx, 4
0x18026d394  jnz     loc_18026D57E
0x18026d39a  mov     rcx, [rcx+0C8h]
0x18026d3a1  mov     rdx, r8; pidlChild
0x18026d3a4  mov     rcx, [rcx+18h]; pidlParent
0x18026d3a8  call    cs:__imp_ILFindChild
0x18026d3af  nop     dword ptr [rax+rax+00h]
0x18026d3b4  xor     r12d, r12d
0x18026d3b7  mov     r14, rax
0x18026d3ba  test    rax, rax
0x18026d3bd  jz      loc_18026D57E
0x18026d3c3  cmp     [rax], r12w
0x18026d3c7  jz      short loc_18026D3DB
0x18026d3c9  movzx   eax, word ptr [rax]
0x18026d3cc  add     rax, r14
0x18026d3cf  jz      short loc_18026D3DB
0x18026d3d1  cmp     [rax], r12w
0x18026d3d5  jnz     loc_18026D57E
0x18026d3db  lea     rcx, [rbp+var_20]
0x18026d3df  mov     [rbp+var_20], r12
0x18026d3e3  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IImmersiveMonitor>>)
0x18026d3e8  mov     rcx, [rsi+0C8h]
0x18026d3ef  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18026d3f6  mov     r8, r14; pidl
0x18026d3f9  mov     [rsp+50h+ppvItem], rax; ppvItem
0x18026d3fe  xor     edx, edx; psfParent
0x18026d400  mov     rcx, [rcx+18h]; pidlParent
0x18026d404  call    cs:__imp_SHCreateItemWithParent
0x18026d40b  nop     dword ptr [rax+rax+00h]
0x18026d410  test    eax, eax
0x18026d412  js      loc_18026D575
0x18026d418  lea     rcx, [rbp+ppv]
0x18026d41c  mov     [rbp+ppv], r12
0x18026d420  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18026d425  xor     edx, edx; pUnkOuter
0x18026d427  lea     rax, [rbp+ppv]
0x18026d42b  lea     r9, _GUID_d54e68c2_54cd_48b3_ad9a_3f4a4503ba80; riid
0x18026d432  mov     [rsp+50h+ppvItem], rax; ppv
0x18026d437  lea     rcx, CLSID_BackgroundTaskCapability; rclsid
0x18026d43e  lea     r8d, [rdx+1]; dwClsContext
0x18026d442  call    cs:__imp_CoCreateInstance
0x18026d449  nop     dword ptr [rax+rax+00h]
0x18026d44e  test    eax, eax
0x18026d450  js      loc_18026D56C
0x18026d456  mov     rdi, [rbp+var_20]
0x18026d45a  xor     ecx, ecx; pv
0x18026d45c  mov     [rbp+pv], r12
0x18026d460  mov     rax, [rdi]
0x18026d463  mov     rbx, [rax+88h]
0x18026d46a  call    cs:__imp_CoTaskMemFree
0x18026d471  nop     dword ptr [rax+rax+00h]
0x18026d476  lea     r8, [rbp+pv]
0x18026d47a  mov     rcx, rdi
0x18026d47d  lea     rdx, PKEY_AppUserModel_ID
0x18026d484  mov     rax, rbx
0x18026d487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026d48c  test    eax, eax
0x18026d48e  js      loc_18026D55C
0x18026d494  mov     [rbp+arg_8], r12d
0x18026d498  cmp     r15d, 4
0x18026d49c  jnz     short loc_18026D4A4
0x18026d49e  lea     edi, [r15-3]
0x18026d4a2  jmp     short loc_18026D4D5
0x18026d4a4  mov     r8, [rsi+0C8h]
0x18026d4ab  lea     r9, [rbp+arg_8]
0x18026d4af  mov     rdx, [rbp+ppv]
0x18026d4b3  mov     rcx, [rbp+var_20]
0x18026d4b7  mov     r8d, [r8+20h]
0x18026d4bb  call    ?IsAppLockScreenCapable@@YAJPEAUIShellItem2@@PEAUIBackgroundTaskCapability@@W4LOCK_SCREEN_APPLICATION_CAPABILITIES@@PEAH@Z; IsAppLockScreenCapable(IShellItem2 *,IBackgroundTaskCapability *,LOCK_SCREEN_APPLICATION_CAPABILITIES,int *)
0x18026d4c0  test    eax, eax
0x18026d4c2  js      loc_18026D55C
0x18026d4c8  mov     edi, r12d
0x18026d4cb  cmp     [rbp+arg_8], r12d
0x18026d4cf  jz      loc_18026D55C
0x18026d4d5  mov     rax, [rsi+0C8h]
0x18026d4dc  cmp     [rax+30h], r12d
0x18026d4e0  jz      short loc_18026D51F
0x18026d4e2  mov     r15, [rbp+pv]
0x18026d4e6  mov     ebx, r12d
0x18026d4e9  mov     rdx, [rsi+0C8h]
0x18026d4f0  cmp     ebx, [rdx+30h]
0x18026d4f3  jnb     short loc_18026D55C
0x18026d4f5  mov     eax, ebx
0x18026d4f7  lea     r8, [rbp+var_10]
0x18026d4fb  mov     [rbp+var_10], r12
0x18026d4ff  lea     rcx, [rax+rax*4]
0x18026d503  mov     rax, [rdx+28h]
0x18026d507  lea     rcx, [rcx+1]
0x18026d50b  mov     rdx, r15
0x18026d50e  lea     rcx, [rax+rcx*8]
0x18026d512  call    ?Find@?$CSimpleStringArrayBase@VCSimpleArrayCaseInsensitiveOrdinalStringCompareHelper@@@@QEBAJPEBGPEA_K_K@Z; CSimpleStringArrayBase<CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::Find(ushort const *,unsigned __int64 *,unsigned __int64)
0x18026d517  test    eax, eax
0x18026d519  jns     short loc_18026D51F
0x18026d51b  inc     ebx
0x18026d51d  jmp     short loc_18026D4E9
0x18026d51f  mov     rcx, r14; pidl
0x18026d522  call    cs:__imp_ILClone
0x18026d529  nop     dword ptr [rax+rax+00h]
0x18026d52e  mov     rcx, [rsi+0C8h]; this
0x18026d535  lea     edx, [rdi+40Ah]; unsigned int
0x18026d53b  mov     r9, rax; __int64
0x18026d53e  xor     r8d, r8d; unsigned __int64
0x18026d541  mov     rbx, rax
0x18026d544  call    ?PostMessageW@CAppListHelper@@QEAA_NI_K_J@Z; CAppListHelper::PostMessageW(uint,unsigned __int64,__int64)
0x18026d549  test    al, al
0x18026d54b  jnz     short loc_18026D55C
0x18026d54d  mov     rcx, rbx; pidl
0x18026d550  call    cs:__imp_ILFree
0x18026d557  nop     dword ptr [rax+rax+00h]
0x18026d55c  mov     rcx, [rbp+pv]; pv
0x18026d560  call    cs:__imp_CoTaskMemFree
0x18026d567  nop     dword ptr [rax+rax+00h]
0x18026d56c  lea     rcx, [rbp+ppv]
0x18026d570  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18026d575  lea     rcx, [rbp+var_20]
0x18026d579  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18026d57e  lea     r11, [rsp+50h+var_s0]
0x18026d583  mov     rbx, [r11+30h]
0x18026d587  mov     rsi, [r11+40h]
0x18026d58b  mov     rsp, r11
0x18026d58e  pop     r15
0x18026d590  pop     r14
0x18026d592  pop     r12
0x18026d594  pop     rdi
0x18026d595  pop     rbp
0x18026d596  retn
```
