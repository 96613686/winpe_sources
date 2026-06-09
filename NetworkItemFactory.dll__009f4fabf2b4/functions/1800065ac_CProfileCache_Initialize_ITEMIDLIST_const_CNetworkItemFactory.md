# CProfileCache::Initialize(_ITEMIDLIST const *,CNetworkItemFactory *)

- ea: `0x1800065ac`
- end: `0x1800066e2`
- name: `?Initialize@CProfileCache@@QEAAJPEFBU_ITEMIDLIST@@PEAVCNetworkItemFactory@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(CProfileCache *__hidden this, LPCITEMIDLIST pidl, struct CNetworkItemFactory *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000636c`

## callees

- `0x18000589c`
- `0x1800065ac`
- `0x1800066e8`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006682`
- `KERNEL32!GetLastError` at `0x180006682`
- `KERNEL32!WaitForSingleObject` at `0x1800066b3`
- `KERNEL32!WaitForSingleObject` at `0x1800066b3`
- `KERNEL32!CreateEventW` at `0x18000662e`
- `KERNEL32!CreateEventW` at `0x180006642`
- `KERNEL32!CreateEventW` at `0x18000662e`
- `KERNEL32!CreateEventW` at `0x180006642`
- `SHELL32!__imp_ILClone` at `0x1800065ff`
- `SHELL32!__imp_ILClone` at `0x1800065ff`
- `SHLWAPI!__imp_SHCreateThread` at `0x180006678`
- `SHLWAPI!__imp_SHCreateThread` at `0x180006678`

## pseudocode

```c
__int64 __fastcall CProfileCache::Initialize(CProfileCache *this, LPCITEMIDLIST pidl, struct CNetworkItemFactory *a3)
{
  LPITEMIDLIST v6; // rax
  signed int v7; // ebx
  HANDLE EventW; // rax
  bool v9; // zf
  signed int LastError; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_cf095e51d6be376dc6c0faef7764f3c8_Traceguids);
  }
  *((_QWORD *)this + 13) = a3;
  v6 = ILClone(pidl);
  *((_QWORD *)this + 12) = v6;
  if ( v6 )
  {
    *((_DWORD *)this + 19) = -2147467259;
    *((_QWORD *)this + 8) = CreateEventW(0, 1, 0, 0);
    EventW = CreateEventW(0, 1, 0, 0);
    v9 = *((_QWORD *)this + 8) == 0;
    *((_QWORD *)this + 7) = EventW;
    if ( v9 || !EventW )
      return (unsigned int)-2147467259;
    (*(void (__fastcall **)(CProfileCache *))(*(_QWORD *)this + 8LL))(this);
    if ( !SHCreateThread(BackgroundInitializeHandler, this, 0x10u, 0) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 < 0 )
      {
        (*(void (__fastcall **)(CProfileCache *))(*(_QWORD *)this + 16LL))(this);
        return (unsigned int)v7;
      }
    }
    if ( WaitForSingleObject(*((HANDLE *)this + 7), 0xFFFFFFFF) )
      return (unsigned int)-2147467259;
    v7 = *((_DWORD *)this + 19);
    if ( v7 < 0 )
      CProfileCache::NotifyBackgroundThread(this);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800065ac  mov     [rsp+arg_0], rbx
0x1800065b1  mov     [rsp+arg_8], rsi
0x1800065b6  push    rdi
0x1800065b7  sub     rsp, 20h
0x1800065bb  mov     rbx, r8
0x1800065be  mov     rsi, rdx
0x1800065c1  mov     rdi, rcx
0x1800065c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065cb  lea     rax, WPP_GLOBAL_Control
0x1800065d2  cmp     rcx, rax
0x1800065d5  jz      short loc_1800065F8
0x1800065d7  cmp     byte ptr [rcx+19h], 4
0x1800065db  jb      short loc_1800065F8
0x1800065dd  test    byte ptr [rcx+1Ch], 2
0x1800065e1  jz      short loc_1800065F8
0x1800065e3  mov     rcx, [rcx+10h]
0x1800065e7  lea     r8, WPP_cf095e51d6be376dc6c0faef7764f3c8_Traceguids
0x1800065ee  mov     edx, 0Ah
0x1800065f3  call    WPP_SF_
0x1800065f8  mov     rcx, rsi; pidl
0x1800065fb  mov     [rdi+68h], rbx
0x1800065ff  call    cs:__imp_ILClone
0x180006605  mov     [rdi+60h], rax
0x180006609  test    rax, rax
0x18000660c  jnz     short loc_180006618
0x18000660e  mov     ebx, 8007000Eh
0x180006613  jmp     loc_1800066D0
0x180006618  xor     r9d, r9d; lpName
0x18000661b  mov     esi, 80004005h
0x180006620  xor     r8d, r8d; bInitialState
0x180006623  mov     [rdi+4Ch], esi
0x180006626  xor     ecx, ecx; lpEventAttributes
0x180006628  lea     ebx, [r9+1]
0x18000662c  mov     edx, ebx; bManualReset
0x18000662e  call    cs:__imp_CreateEventW
0x180006634  xor     r9d, r9d; lpName
0x180006637  xor     r8d, r8d; bInitialState
0x18000663a  mov     edx, ebx; bManualReset
0x18000663c  mov     [rdi+40h], rax
0x180006640  xor     ecx, ecx; lpEventAttributes
0x180006642  call    cs:__imp_CreateEventW
0x180006648  cmp     qword ptr [rdi+40h], 0
0x18000664d  mov     [rdi+38h], rax
0x180006651  jz      short loc_1800066CE
0x180006653  test    rax, rax
0x180006656  jz      short loc_1800066CE
0x180006658  mov     rax, [rdi]
0x18000665b  mov     rcx, rdi
0x18000665e  mov     rax, [rax+8]
0x180006662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006667  xor     r9d, r9d; pfnCallback
0x18000666a  lea     r8d, [rbx+0Fh]; flags
0x18000666e  mov     rdx, rdi; pData
0x180006671  lea     rcx, ?BackgroundInitializeHandler@@YAKPEAX@Z; pfnThreadProc
0x180006678  call    cs:__imp_SHCreateThread
0x18000667e  test    eax, eax
0x180006680  jnz     short loc_1800066AC
0x180006682  call    cs:__imp_GetLastError
0x180006688  mov     ebx, eax
0x18000668a  test    eax, eax
0x18000668c  jle     short loc_180006697
0x18000668e  movzx   ebx, ax
0x180006691  or      ebx, 80070000h
0x180006697  test    ebx, ebx
0x180006699  jns     short loc_1800066AC
0x18000669b  mov     rax, [rdi]
0x18000669e  mov     rcx, rdi
0x1800066a1  mov     rax, [rax+10h]
0x1800066a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066aa  jmp     short loc_1800066D0
0x1800066ac  mov     rcx, [rdi+38h]; hHandle
0x1800066b0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800066b3  call    cs:__imp_WaitForSingleObject
0x1800066b9  test    eax, eax
0x1800066bb  jnz     short loc_1800066CE
0x1800066bd  mov     ebx, [rdi+4Ch]
0x1800066c0  test    ebx, ebx
0x1800066c2  jns     short loc_1800066D0
0x1800066c4  mov     rcx, rdi; this
0x1800066c7  call    ?NotifyBackgroundThread@CProfileCache@@QEAAXXZ; CProfileCache::NotifyBackgroundThread(void)
0x1800066cc  jmp     short loc_1800066D0
0x1800066ce  mov     ebx, esi
0x1800066d0  mov     rsi, [rsp+28h+arg_8]
0x1800066d5  mov     eax, ebx
0x1800066d7  mov     rbx, [rsp+28h+arg_0]
0x1800066dc  add     rsp, 20h
0x1800066e0  pop     rdi
0x1800066e1  retn
```
