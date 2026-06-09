# UICollection::DestroyDirection(REALIZEDIRECTION,int)

- ea: `0x18001b970`
- end: `0x18001bc85`
- name: `?DestroyDirection@UICollection@@UEAAXW4REALIZEDIRECTION@@H@Z`
- size: `789`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800173a0`
- `0x18001b970`
- `0x18001bc90`
- `0x18001c08c`
- `0x18013f7d0`
- `0x1801406ec`
- `0x1801e4538`
- `0x180210010`

## import_xrefs

- `SHCORE!SHCreateThread` at `0x18001bc4f`
- `SHCORE!SHCreateThread` at `0x18001bc4f`
- `SHLWAPI!SHRegGetBoolUSValueW` at `0x18001b9db`
- `SHLWAPI!SHRegGetBoolUSValueW` at `0x18001b9db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b9b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b9b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001bbdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001bbdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bbd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bbe6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bbd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bbe6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bc59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bc59`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001bc11`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001bc11`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001bbc6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001bbc6`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001ba30`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001bac1`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001ba30`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001bac1`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001ba25`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001bab6`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001ba25`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001bab6`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001ba19`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001baaa`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001ba19`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001baaa`

## pseudocode

```c
void __fastcall UICollection::DestroyDirection(__int64 *a1, unsigned int a2, int a3)
{
  DirectUI::Element *v3; // r12
  DirectUI::Value *Value; // rbx
  int Int; // edi
  __int64 v9; // rax
  unsigned int v10; // r15d
  DirectUI::Element *ItemLayout; // rax
  DirectUI::Value *v12; // rdi
  unsigned int v13; // ebx
  __int64 v14; // r8
  __int64 v15; // rdx
  struct ItemLayout *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v21; // rax
  int Data; // [rsp+40h] [rbp-69h] BYREF
  HANDLE TargetHandle; // [rsp+48h] [rbp-61h] BYREF
  HANDLE pData; // [rsp+50h] [rbp-59h] BYREF
  __int64 v25; // [rsp+58h] [rbp-51h]
  _BYTE v26[8]; // [rsp+60h] [rbp-49h] BYREF
  int v27; // [rsp+68h] [rbp-41h]
  int v28; // [rsp+78h] [rbp-31h]
  int v29; // [rsp+A8h] [rbp-1h]
  int v30; // [rsp+ACh] [rbp+3h]
  unsigned int v31; // [rsp+B0h] [rbp+7h]
  unsigned int v32; // [rsp+B4h] [rbp+Bh]

  v3 = (DirectUI::Element *)(a1 - 27);
  if ( *((_DWORD *)a1 + 16) )
  {
    g_dwReentrantThreadId = GetCurrentThreadId();
    g_ReentrantCheck = 4;
    if ( !SHRegGetBoolUSValueW(
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
            L"ShellViewReentered",
            0,
            0) )
    {
      Data = 1;
      RegSetKeyValueW(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
        L"ShellViewReentered",
        4u,
        &Data,
        4u);
      TargetHandle = 0;
      CurrentProcess = GetCurrentProcess();
      CurrentThread = GetCurrentThread();
      v21 = GetCurrentProcess();
      if ( DuplicateHandle(v21, CurrentThread, CurrentProcess, &TargetHandle, 0x1FFFFFu, 1, 0) )
      {
        pData = TargetHandle;
        v25 = 0;
        LODWORD(v25) = ComputeStackHash();
        SHCreateThread(
          DirectUI::PatternProvider<UIItemsViewScrollProvider,IScrollProvider,5>::GetProxyCreator,
          &pData,
          0x200u,
          s_SendWERForReentrancy);
        CloseHandle(TargetHandle);
      }
    }
  }
  if ( a3 < 0 || a3 >= (*(int (__fastcall **)(__int64 *))(*a1 + 56))(a1) )
    return;
  Value = DirectUI::Element::GetValue(v3, UICollection::HeaderScrollTicksProp, 2, 0);
  Int = DirectUI::Value::GetInt(Value);
  DirectUI::Value::Release(Value);
  if ( a3 < Int )
  {
    if ( a2 != 1 )
      return;
LABEL_29:
    v14 = 0;
    v15 = 1;
LABEL_12:
    UICollection::_DestroyItems(v3, v15, v14);
    return;
  }
  if ( a3 < (int)(Int + UICollection::GetLayoutTickCount(v3)) )
  {
    memset_0(v26, 0, 0x58u);
    v9 = *a1;
    v28 = -1;
    (*(void (__fastcall **)(__int64 *, _QWORD, _BYTE *))(v9 + 72))(a1, (unsigned int)a3, v26);
    if ( a2 == 1 )
    {
      v10 = v31;
      if ( a3 > v29 )
        goto LABEL_15;
    }
    else
    {
      v10 = v32;
    }
    if ( a2 != -1 || a3 >= v30 )
    {
LABEL_10:
      ItemLayout = UICollection::GetItemLayout(v3);
      v12 = DirectUI::Element::GetValue(ItemLayout, ItemLayout::ItemCountProp, 2, 0);
      v13 = DirectUI::Value::GetInt(v12);
      DirectUI::Value::Release(v12);
      if ( v10 >= v13 )
        return;
      v14 = v10;
      v15 = a2;
      goto LABEL_12;
    }
LABEL_15:
    if ( v27 == 3 && v32 - v31 == 1 )
    {
      v16 = UICollection::GetItemLayout(v3);
      v17 = (*(__int64 (__fastcall **)(struct ItemLayout *, _QWORD))(*(_QWORD *)v16 + 368LL))(v16, v31);
      if ( v17 )
      {
        v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 424LL))(v17);
        if ( v18 )
        {
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v18 + 8LL))(v18, a2, (unsigned int)(a3 - v29));
          if ( a2 == 1 )
            v10 = v32;
          else
            v10 = v31 - 1;
        }
      }
    }
    goto LABEL_10;
  }
  if ( a2 == -1 )
    goto LABEL_29;
}

```

## disassembly

```asm
0x18001b970  push    rbp
0x18001b972  push    rbx
0x18001b973  push    rsi
0x18001b974  push    rdi
0x18001b975  push    r12
0x18001b977  push    r14
0x18001b979  push    r15
0x18001b97b  lea     rbp, [rsp-27h]
0x18001b980  sub     rsp, 0D0h
0x18001b987  mov     rax, cs:__security_cookie
0x18001b98e  xor     rax, rsp
0x18001b991  mov     [rbp+57h+var_40], rax
0x18001b995  lea     r12, [rcx-0D8h]
0x18001b99c  mov     esi, r8d
0x18001b99f  cmp     dword ptr [r12+118h], 0
0x18001b9a8  mov     r14d, edx
0x18001b9ab  mov     r15, rcx
0x18001b9ae  jz      short loc_18001B9E9
0x18001b9b0  call    cs:__imp_GetCurrentThreadId
0x18001b9b6  mov     cs:?g_dwReentrantThreadId@@3KC, eax; ulong volatile g_dwReentrantThreadId
0x18001b9bc  mov     ebx, 4
0x18001b9c1  lea     rdx, ValueName; "ShellViewReentered"
0x18001b9c8  mov     cs:?g_ReentrantCheck@@3W4REENTRANCYCHECKTHATFAILED@@C, ebx; REENTRANCYCHECKTHATFAILED volatile g_ReentrantCheck
0x18001b9ce  xor     r9d, r9d; fDefault
0x18001b9d1  lea     rcx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001b9d8  xor     r8d, r8d; fIgnoreHKCU
0x18001b9db  call    cs:__imp_SHRegGetBoolUSValueW
0x18001b9e1  test    eax, eax
0x18001b9e3  jz      loc_18001BB9A
0x18001b9e9  test    esi, esi
0x18001b9eb  js      loc_18001BADA
0x18001b9f1  mov     rax, [r15]
0x18001b9f4  mov     rcx, r15
0x18001b9f7  mov     rax, [rax+38h]
0x18001b9fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba00  cmp     esi, eax
0x18001ba02  jge     loc_18001BADA
0x18001ba08  xor     r9d, r9d
0x18001ba0b  lea     rdx, ?HeaderScrollTicksProp@UICollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UICollection::HeaderScrollTicksProp(void)
0x18001ba12  mov     rcx, r12
0x18001ba15  lea     r8d, [r9+2]
0x18001ba19  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18001ba1f  mov     rcx, rax
0x18001ba22  mov     rbx, rax
0x18001ba25  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18001ba2b  mov     rcx, rbx
0x18001ba2e  mov     edi, eax
0x18001ba30  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001ba36  cmp     esi, edi
0x18001ba38  jl      loc_18001BC6F
0x18001ba3e  mov     rcx, r12; this
0x18001ba41  call    ?GetLayoutTickCount@UICollection@@QEAAHXZ; UICollection::GetLayoutTickCount(void)
0x18001ba46  add     eax, edi
0x18001ba48  cmp     esi, eax
0x18001ba4a  jge     loc_18001BC64
0x18001ba50  xor     edx, edx; Val
0x18001ba52  lea     rcx, [rbp+57h+var_A0]; void *
0x18001ba56  lea     r8d, [rdx+58h]; Size
0x18001ba5a  call    memset_0
0x18001ba5f  mov     rax, [r15]
0x18001ba62  lea     r8, [rbp+57h+var_A0]
0x18001ba66  mov     edx, esi
0x18001ba68  mov     [rbp+57h+var_88], 0FFFFFFFFh
0x18001ba6f  mov     rcx, r15
0x18001ba72  mov     rax, [rax+48h]
0x18001ba76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba7b  mov     eax, [rbp+57h+var_4C]
0x18001ba7e  cmp     r14d, 1
0x18001ba82  jz      short loc_18001BAF8
0x18001ba84  mov     r15d, eax
0x18001ba87  cmp     r14d, 0FFFFFFFFh
0x18001ba8b  jz      loc_18001BB80
0x18001ba91  mov     rcx, r12; this
0x18001ba94  call    ?GetItemLayout@UICollection@@QEAAPEAVItemLayout@@XZ; UICollection::GetItemLayout(void)
0x18001ba99  xor     r9d, r9d
0x18001ba9c  lea     rdx, ?ItemCountProp@ItemLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemLayout::ItemCountProp(void)
0x18001baa3  mov     rcx, rax
0x18001baa6  lea     r8d, [r9+2]
0x18001baaa  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18001bab0  mov     rcx, rax
0x18001bab3  mov     rdi, rax
0x18001bab6  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18001babc  mov     rcx, rdi
0x18001babf  mov     ebx, eax
0x18001bac1  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001bac7  cmp     r15d, ebx
0x18001baca  jnb     short loc_18001BADA
0x18001bacc  mov     r8d, r15d
0x18001bacf  mov     edx, r14d
0x18001bad2  mov     rcx, r12
0x18001bad5  call    ?_DestroyItems@UICollection@@IEAAXW4REALIZEDIRECTION@@I@Z; UICollection::_DestroyItems(REALIZEDIRECTION,uint)
0x18001bada  mov     rcx, [rbp+57h+var_40]
0x18001bade  xor     rcx, rsp; StackCookie
0x18001bae1  call    __security_check_cookie
0x18001bae6  add     rsp, 0D0h
0x18001baed  pop     r15
0x18001baef  pop     r14
0x18001baf1  pop     r12
0x18001baf3  pop     rdi
0x18001baf4  pop     rsi
0x18001baf5  pop     rbx
0x18001baf6  pop     rbp
0x18001baf7  retn
0x18001baf8  mov     r15d, [rbp+57h+var_50]
0x18001bafc  cmp     esi, [rbp+57h+var_58]
0x18001baff  jle     short loc_18001BA87
0x18001bb01  cmp     [rbp+57h+var_98], 3
0x18001bb05  jnz     short loc_18001BA91
0x18001bb07  sub     eax, [rbp+57h+var_50]
0x18001bb0a  cmp     eax, 1
0x18001bb0d  jnz     short loc_18001BA91
0x18001bb0f  mov     rcx, r12; this
0x18001bb12  call    ?GetItemLayout@UICollection@@QEAAPEAVItemLayout@@XZ; UICollection::GetItemLayout(void)
0x18001bb17  mov     edx, [rbp+57h+var_50]
0x18001bb1a  mov     r8, rax
0x18001bb1d  mov     rcx, [rax]
0x18001bb20  mov     rax, [rcx+170h]
0x18001bb27  mov     rcx, r8
0x18001bb2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb2f  mov     rdx, rax
0x18001bb32  test    rax, rax
0x18001bb35  jz      loc_18001BA91
0x18001bb3b  mov     rcx, [rax]
0x18001bb3e  mov     rax, [rcx+1A8h]
0x18001bb45  mov     rcx, rdx
0x18001bb48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb4d  mov     r9, rax
0x18001bb50  test    rax, rax
0x18001bb53  jz      loc_18001BA91
0x18001bb59  mov     rcx, [rax]
0x18001bb5c  mov     edx, r14d
0x18001bb5f  sub     esi, [rbp+57h+var_58]
0x18001bb62  mov     r8d, esi
0x18001bb65  mov     rax, [rcx+8]
0x18001bb69  mov     rcx, r9
0x18001bb6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb71  cmp     r14d, 1
0x18001bb75  jnz     short loc_18001BB8E
0x18001bb77  mov     r15d, [rbp+57h+var_4C]
0x18001bb7b  jmp     loc_18001BA91
0x18001bb80  cmp     esi, [rbp+57h+var_54]
0x18001bb83  jge     loc_18001BA91
0x18001bb89  jmp     loc_18001BB01
0x18001bb8e  mov     r15d, [rbp+57h+var_50]
0x18001bb92  dec     r15d
0x18001bb95  jmp     loc_18001BA91
0x18001bb9a  lea     rax, [rbp+57h+Data]
0x18001bb9e  mov     [rsp+100h+cbData], ebx; cbData
0x18001bba2  mov     r9d, ebx; dwType
0x18001bba5  mov     [rsp+100h+lpData], rax; lpData
0x18001bbaa  lea     r8, ValueName; "ShellViewReentered"
0x18001bbb1  mov     [rbp+57h+Data], 1
0x18001bbb8  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001bbbf  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001bbc6  call    cs:__imp_RegSetKeyValueW
0x18001bbcc  mov     [rbp+57h+TargetHandle], 0
0x18001bbd4  call    cs:__imp_GetCurrentProcess
0x18001bbda  mov     rdi, rax
0x18001bbdd  call    cs:__imp_GetCurrentThread
0x18001bbe3  mov     rbx, rax
0x18001bbe6  call    cs:__imp_GetCurrentProcess
0x18001bbec  mov     [rsp+100h+dwOptions], 0; dwOptions
0x18001bbf4  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x18001bbf8  mov     rcx, rax; hSourceProcessHandle
0x18001bbfb  mov     [rsp+100h+cbData], 1; bInheritHandle
0x18001bc03  mov     r8, rdi; hTargetProcessHandle
0x18001bc06  mov     dword ptr [rsp+100h+lpData], 1FFFFFh; dwDesiredAccess
0x18001bc0e  mov     rdx, rbx; hSourceHandle
0x18001bc11  call    cs:__imp_DuplicateHandle
0x18001bc17  test    eax, eax
0x18001bc19  jz      loc_18001B9E9
0x18001bc1f  mov     rax, [rbp+57h+TargetHandle]
0x18001bc23  mov     [rbp+57h+pData], rax
0x18001bc27  mov     [rbp+57h+var_A8], 0
0x18001bc2f  call    ?ComputeStackHash@@YAKXZ; ComputeStackHash(void)
0x18001bc34  lea     r9, ?s_SendWERForReentrancy@@YAKPEAX@Z; pfnCallback
0x18001bc3b  mov     dword ptr [rbp+57h+var_A8], eax
0x18001bc3e  mov     r8d, 200h; flags
0x18001bc44  lea     rdx, [rbp+57h+pData]; pData
0x18001bc48  lea     rcx, ?GetProxyCreator@?$PatternProvider@VUIItemsViewScrollProvider@@UIScrollProvider@@$04@DirectUI@@UEAAP6APEAVProviderProxy@2@PEAVElement@2@@ZXZ; pfnThreadProc
0x18001bc4f  call    cs:__imp_SHCreateThread
0x18001bc55  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x18001bc59  call    cs:__imp_CloseHandle
0x18001bc5f  jmp     loc_18001B9E9
0x18001bc64  cmp     r14d, 0FFFFFFFFh
0x18001bc68  jz      short loc_18001BC79
0x18001bc6a  jmp     loc_18001BADA
0x18001bc6f  cmp     r14d, 1
0x18001bc73  jnz     loc_18001BADA
0x18001bc79  xor     r8d, r8d
0x18001bc7c  lea     edx, [r8+1]
0x18001bc80  jmp     loc_18001BAD2
```
