# Wallet::WalletItemManager::Initialize(ushort const *)

- ea: `0x180023e80`
- end: `0x180024033`
- name: `?Initialize@WalletItemManager@Wallet@@UEAAJPEBG@Z`
- size: `435`
- prototype: `__int64 __fastcall(Wallet::WalletItemManager *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002214`
- `0x18000d3fc`
- `0x180023e80`
- `0x180043052`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180023f67`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180023f67`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180023f20`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180023f20`

## pseudocode

```c
__int64 __fastcall Wallet::WalletItemManager::Initialize(Wallet::WalletItemManager *this, const unsigned __int16 *a2)
{
  char *v4; // rax
  __int64 v5; // r8
  int v6; // edi
  __int64 v7; // rcx
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  CHAR v10[16]; // [rsp+40h] [rbp-148h] BYREF
  CHAR MultiByteStr[2]; // [rsp+50h] [rbp-138h] BYREF
  _BYTE v12[270]; // [rsp+52h] [rbp-136h] BYREF

  v4 = (char *)operator new(0x70u);
  if ( v4 )
  {
    *((_DWORD *)v4 + 2) = 0;
    *(_QWORD *)v4 = &Wallet::WalletDatabaseESE::`vftable';
    *((_QWORD *)v4 + 2) = -1;
    *((_QWORD *)v4 + 3) = -1;
    *((_DWORD *)v4 + 8) = -1;
    *(_QWORD *)(v4 + 36) = 0;
    *((_QWORD *)v4 + 6) = 0;
    *((_QWORD *)v4 + 7) = 0;
    *((_DWORD *)v4 + 16) = 0;
    *((_QWORD *)v4 + 9) = 0;
    *((_QWORD *)v4 + 10) = 0;
    *((_QWORD *)v4 + 11) = 0;
    *((_DWORD *)v4 + 24) = 1;
    *((_QWORD *)v4 + 13) = 0;
  }
  else
  {
    v4 = 0;
  }
  *((_QWORD *)this + 7) = v4;
  if ( !v4 )
  {
    v6 = -2147024882;
LABEL_11:
    *((_DWORD *)this + 12) = 0;
    goto LABEL_13;
  }
  CreateDirectoryW(a2, 0);
  *(_WORD *)MultiByteStr = 0;
  memset_0(v12, 0, 0x102u);
  if ( !WideCharToMultiByte(0xFDE9u, 0, a2, -1, MultiByteStr, 260, 0, 0) )
  {
    v6 = -2147467259;
    goto LABEL_11;
  }
  if ( (Microsoft_Windows_WalletEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(MICROSOFT_WINDOWS_WALLET_Context, Core_OpenDatabase_Start, v5, 1, v10);
  v7 = *((_QWORD *)this + 7);
  *((_DWORD *)this + 12) = 1;
  v6 = (*(__int64 (__fastcall **)(__int64, CHAR *))(*(_QWORD *)v7 + 8LL))(v7, MultiByteStr);
  if ( v6 < 0 )
    goto LABEL_11;
  v6 = 0;
LABEL_13:
  if ( (Microsoft_Windows_WalletEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(MICROSOFT_WINDOWS_WALLET_Context, Core_OpenDatabase_Stop, v5, 1, v10);
  if ( !*((_DWORD *)this + 12) )
  {
    v8 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 7);
    if ( v8 )
    {
      (**v8)(v8, 1);
      *((_QWORD *)this + 7) = 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180023e80  mov     [rsp+arg_10], rbx
0x180023e85  push    rbp
0x180023e86  push    rsi
0x180023e87  push    rdi
0x180023e88  sub     rsp, 170h
0x180023e8f  mov     rax, cs:__security_cookie
0x180023e96  xor     rax, rsp
0x180023e99  mov     [rsp+188h+var_28], rax
0x180023ea1  mov     rbx, rcx
0x180023ea4  mov     rdi, rdx
0x180023ea7  mov     ecx, 70h ; 'p'; Size
0x180023eac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023eb1  xor     esi, esi
0x180023eb3  mov     ebp, 1
0x180023eb8  test    rax, rax
0x180023ebb  jz      short loc_180023F05
0x180023ebd  mov     [rax+8], esi
0x180023ec0  lea     rcx, ??_7WalletDatabaseESE@Wallet@@6B@; const Wallet::WalletDatabaseESE::`vftable'
0x180023ec7  mov     [rax], rcx
0x180023eca  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x180023ed2  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180023eda  mov     dword ptr [rax+20h], 0FFFFFFFFh
0x180023ee1  mov     [rax+24h], rsi
0x180023ee5  mov     [rax+30h], rsi
0x180023ee9  mov     [rax+38h], rsi
0x180023eed  mov     [rax+40h], esi
0x180023ef0  mov     [rax+48h], rsi
0x180023ef4  mov     [rax+50h], rsi
0x180023ef8  mov     [rax+58h], rsi
0x180023efc  mov     [rax+60h], ebp
0x180023eff  mov     [rax+68h], rsi
0x180023f03  jmp     short loc_180023F08
0x180023f05  mov     rax, rsi
0x180023f08  mov     [rbx+38h], rax
0x180023f0c  test    rax, rax
0x180023f0f  jnz     short loc_180023F1B
0x180023f11  mov     edi, 8007000Eh
0x180023f16  jmp     loc_180023FBF
0x180023f1b  xor     edx, edx; lpSecurityAttributes
0x180023f1d  mov     rcx, rdi; lpPathName
0x180023f20  call    cs:__imp_CreateDirectoryW
0x180023f26  xor     edx, edx; Val
0x180023f28  mov     word ptr [rsp+188h+MultiByteStr], si
0x180023f2d  mov     r8d, 102h; Size
0x180023f33  lea     rcx, [rsp+188h+var_136]; void *
0x180023f38  call    memset_0
0x180023f3d  mov     [rsp+188h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x180023f42  lea     rax, [rsp+188h+MultiByteStr]
0x180023f47  mov     [rsp+188h+lpDefaultChar], rsi; lpDefaultChar
0x180023f4c  or      r9d, 0FFFFFFFFh; cchWideChar
0x180023f50  mov     [rsp+188h+cbMultiByte], 104h; cbMultiByte
0x180023f58  mov     r8, rdi; lpWideCharStr
0x180023f5b  xor     edx, edx; dwFlags
0x180023f5d  mov     [rsp+188h+lpMultiByteStr], rax; lpMultiByteStr
0x180023f62  mov     ecx, 0FDE9h; CodePage
0x180023f67  call    cs:__imp_WideCharToMultiByte
0x180023f6d  test    eax, eax
0x180023f6f  jnz     short loc_180023F78
0x180023f71  mov     edi, 80004005h
0x180023f76  jmp     short loc_180023FBF
0x180023f78  test    cs:Microsoft_Windows_WalletEnableBits, bpl
0x180023f7f  jz      short loc_180023FA1
0x180023f81  lea     rax, [rsp+188h+var_148]
0x180023f86  mov     r9d, ebp
0x180023f89  lea     rdx, Core_OpenDatabase_Start
0x180023f90  mov     [rsp+188h+lpMultiByteStr], rax
0x180023f95  lea     rcx, MICROSOFT_WINDOWS_WALLET_Context
0x180023f9c  call    McGenEventWrite_EventWriteTransfer
0x180023fa1  mov     rcx, [rbx+38h]
0x180023fa5  lea     rdx, [rsp+188h+MultiByteStr]
0x180023faa  mov     [rbx+30h], ebp
0x180023fad  mov     rax, [rcx]
0x180023fb0  mov     rax, [rax+8]
0x180023fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fb9  mov     edi, eax
0x180023fbb  test    eax, eax
0x180023fbd  jns     short loc_180023FC4
0x180023fbf  mov     [rbx+30h], esi
0x180023fc2  jmp     short loc_180023FC6
0x180023fc4  mov     edi, esi
0x180023fc6  test    cs:Microsoft_Windows_WalletEnableBits, bpl
0x180023fcd  jz      short loc_180023FEF
0x180023fcf  lea     rax, [rsp+188h+var_148]
0x180023fd4  mov     r9d, ebp
0x180023fd7  lea     rdx, Core_OpenDatabase_Stop
0x180023fde  mov     [rsp+188h+lpMultiByteStr], rax
0x180023fe3  lea     rcx, MICROSOFT_WINDOWS_WALLET_Context
0x180023fea  call    McGenEventWrite_EventWriteTransfer
0x180023fef  cmp     [rbx+30h], esi
0x180023ff2  jnz     short loc_18002400E
0x180023ff4  mov     rcx, [rbx+38h]
0x180023ff8  test    rcx, rcx
0x180023ffb  jz      short loc_18002400E
0x180023ffd  mov     r8, [rcx]
0x180024000  mov     edx, ebp
0x180024002  mov     rax, [r8]
0x180024005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002400a  mov     [rbx+38h], rsi
0x18002400e  mov     eax, edi
0x180024010  mov     rcx, [rsp+188h+var_28]
0x180024018  xor     rcx, rsp; StackCookie
0x18002401b  call    __security_check_cookie
0x180024020  mov     rbx, [rsp+188h+arg_10]
0x180024028  add     rsp, 170h
0x18002402f  pop     rdi
0x180024030  pop     rsi
0x180024031  pop     rbp
0x180024032  retn
```
