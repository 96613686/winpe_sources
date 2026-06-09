# WwanProfileHistorian::LoadHistory(void)

- ea: `0x1800bfc7c`
- end: `0x1800bff07`
- name: `?LoadHistory@WwanProfileHistorian@@QEAAJXZ`
- size: `651`
- prototype: `__int64 __fastcall(WwanProfileHistorian *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800b78ec`

## callees

- `0x1800094f4`
- `0x1800bd1b4`
- `0x1800bd1dc`
- `0x1800bfc7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bfcd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bfcd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bfec1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bfec1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bfeb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bfeb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bfd70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bfd70`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bfdb3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bfe1e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bfdb3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bfe1e`
- `MobileNetworking!GetPersistentRegPath` at `0x1800bfd1f`
- `MobileNetworking!GetPersistentRegPath` at `0x1800bfd1f`

## pseudocode

```c
__int64 __fastcall WwanProfileHistorian::LoadHistory(WwanProfileHistorian *this)
{
  LPCRITICAL_SECTION v1; // rbx
  signed int v2; // r8d
  int PersistentRegPath; // eax
  LSTATUS v4; // eax
  LSTATUS ValueW; // eax
  LSTATUS v6; // eax
  int v7; // edi
  signed int v8; // r8d
  signed int OwningThread; // edx
  __int64 v10; // rax
  WwanProfileHistorian *pcbData; // [rsp+70h] [rbp+30h] BYREF
  int v13; // [rsp+78h] [rbp+38h] BYREF
  HKEY hkey; // [rsp+80h] [rbp+40h] BYREF

  pcbData = this;
  v1 = qword_180152B88;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_59efe20e95083d54484ef368743a0c87_Traceguids);
  hkey = 0;
  LODWORD(pcbData) = 0;
  EnterCriticalSection(v1);
  if ( LOBYTE(v1[1].DebugInfo) )
  {
    if ( WwanProfileHistorian::m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot )
      goto LABEL_10;
    v13 = 260;
    PersistentRegPath = GetPersistentRegPath(
                          0,
                          L"MobileBroadbandAccounts\\Data",
                          &v13,
                          &WwanProfileHistorian::m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot);
    v2 = PersistentRegPath;
    if ( PersistentRegPath > 0 )
      v2 = (unsigned __int16)PersistentRegPath | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_10:
      memset_0(*(void **)&v1[1].LockCount, 0, 0x14F0u);
      LODWORD(v1[1].OwningThread) = 0;
      v4 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             &WwanProfileHistorian::m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot,
             0,
             0x20019u,
             &hkey);
      v2 = v4;
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x80070000;
      if ( v2 >= 0 )
      {
        ValueW = RegGetValueW(hkey, 0, L"ProfileHistory", 8u, 0, 0, (LPDWORD)&pcbData);
        v2 = ValueW;
        if ( ValueW > 0 )
          v2 = (unsigned __int16)ValueW | 0x80070000;
        if ( v2 >= 0 )
        {
          if ( (unsigned int)pcbData <= 0x14F0 && (unsigned int)pcbData == 536 * ((unsigned int)pcbData / 0x218uLL) )
          {
            if ( (_DWORD)pcbData )
            {
              v6 = RegGetValueW(
                     hkey,
                     0,
                     L"ProfileHistory",
                     0x20000008u,
                     0,
                     *(PVOID *)&v1[1].LockCount,
                     (LPDWORD)&pcbData);
              v2 = v6;
              if ( v6 > 0 )
                v2 = (unsigned __int16)v6 | 0x80070000;
            }
          }
          else
          {
            v2 = -2147024883;
          }
        }
      }
    }
  }
  else
  {
    v2 = -2147019873;
  }
  v7 = 0;
  if ( v2 != -2147024894 )
    v7 = v2;
  if ( v7 < 0 )
  {
    LODWORD(v1[1].OwningThread) = 0;
    OwningThread = 0;
  }
  else
  {
    v8 = 0;
    OwningThread = (unsigned int)pcbData / 0x218;
    LODWORD(v1[1].OwningThread) = (unsigned int)pcbData / 0x218;
    if ( OwningThread > 0 )
    {
      do
      {
        v10 = v8++;
        *(_WORD *)(536 * v10 + *(_QWORD *)&v1[1].LockCount + 510) = 0;
        OwningThread = (signed int)v1[1].OwningThread;
      }
      while ( v8 < OwningThread );
    }
  }
  memset_0((void *)(*(_QWORD *)&v1[1].LockCount + 536LL * OwningThread), 0, 536LL * (10 - OwningThread));
  if ( hkey )
    RegCloseKey(hkey);
  LeaveCriticalSection(v1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_59efe20e95083d54484ef368743a0c87_Traceguids,
      (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800bfc7c  mov     [rsp-28h+arg_18], rbx
0x1800bfc81  mov     [rsp-28h+arg_0], rcx
0x1800bfc86  push    rbp
0x1800bfc87  push    rsi
0x1800bfc88  push    rdi
0x1800bfc89  push    r12
0x1800bfc8b  push    r15
0x1800bfc8d  mov     rbp, rsp
0x1800bfc90  sub     rsp, 40h
0x1800bfc94  mov     rbx, cs:qword_180152B88
0x1800bfc9b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfca2  lea     r12, WPP_GLOBAL_Control
0x1800bfca9  cmp     rcx, r12
0x1800bfcac  jz      short loc_1800BFCC9
0x1800bfcae  test    byte ptr [rcx+1Ch], 10h
0x1800bfcb2  jz      short loc_1800BFCC9
0x1800bfcb4  mov     rcx, [rcx+10h]
0x1800bfcb8  lea     r8, WPP_59efe20e95083d54484ef368743a0c87_Traceguids
0x1800bfcbf  mov     edx, 0Fh
0x1800bfcc4  call    WPP_SF_
0x1800bfcc9  xor     esi, esi
0x1800bfccb  mov     rcx, rbx; lpCriticalSection
0x1800bfcce  mov     [rbp+hkey], rsi
0x1800bfcd2  mov     dword ptr [rbp+arg_0], esi
0x1800bfcd5  call    cs:__imp_EnterCriticalSection
0x1800bfcdb  mov     r15, 0F4898D5F85BB3951h
0x1800bfce5  cmp     [rbx+28h], sil
0x1800bfce9  jnz     short loc_1800BFCF6
0x1800bfceb  mov     r8d, 8007139Fh
0x1800bfcf1  jmp     loc_1800BFE3A
0x1800bfcf6  cmp     cs:?m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot@WwanProfileHistorian@@0PAGA, si; ushort near * WwanProfileHistorian::m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot
0x1800bfcfd  mov     edi, 80070000h
0x1800bfd02  jnz     short loc_1800BFD3C
0x1800bfd04  lea     r9, ?m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot@WwanProfileHistorian@@0PAGA; ushort near * WwanProfileHistorian::m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot
0x1800bfd0b  mov     [rbp+arg_8], 104h
0x1800bfd12  lea     r8, [rbp+arg_8]
0x1800bfd16  xor     ecx, ecx
0x1800bfd18  lea     rdx, aMobilebroadban_0; "MobileBroadbandAccounts\\Data"
0x1800bfd1f  call    cs:__imp_GetPersistentRegPath
0x1800bfd25  mov     r8d, eax
0x1800bfd28  test    eax, eax
0x1800bfd2a  jle     short loc_1800BFD33
0x1800bfd2c  movzx   r8d, ax
0x1800bfd30  or      r8d, edi
0x1800bfd33  test    r8d, r8d
0x1800bfd36  js      loc_1800BFE3A
0x1800bfd3c  mov     rcx, [rbx+30h]; void *
0x1800bfd40  xor     edx, edx; Val
0x1800bfd42  mov     r8d, 14F0h; Size
0x1800bfd48  call    memset_0
0x1800bfd4d  lea     rax, [rbp+hkey]
0x1800bfd51  mov     [rbx+38h], esi
0x1800bfd54  mov     r9d, 20019h; samDesired
0x1800bfd5a  mov     [rsp+40h+phkResult], rax; phkResult
0x1800bfd5f  xor     r8d, r8d; ulOptions
0x1800bfd62  lea     rdx, ?m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot@WwanProfileHistorian@@0PAGA; lpSubKey
0x1800bfd69  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bfd70  call    cs:__imp_RegOpenKeyExW
0x1800bfd76  mov     r8d, eax
0x1800bfd79  test    eax, eax
0x1800bfd7b  jle     short loc_1800BFD84
0x1800bfd7d  movzx   r8d, ax
0x1800bfd81  or      r8d, edi
0x1800bfd84  test    r8d, r8d
0x1800bfd87  js      loc_1800BFE3A
0x1800bfd8d  mov     rcx, [rbp+hkey]; hkey
0x1800bfd91  lea     rax, [rbp+arg_0]
0x1800bfd95  mov     [rsp+40h+pcbData], rax; pcbData
0x1800bfd9a  lea     r8, aProfilehistory; "ProfileHistory"
0x1800bfda1  mov     [rsp+40h+pvData], rsi; pvData
0x1800bfda6  mov     r9d, 8; dwFlags
0x1800bfdac  xor     edx, edx; lpSubKey
0x1800bfdae  mov     [rsp+40h+phkResult], rsi; pdwType
0x1800bfdb3  call    cs:__imp_RegGetValueW
0x1800bfdb9  mov     r8d, eax
0x1800bfdbc  test    eax, eax
0x1800bfdbe  jle     short loc_1800BFDC7
0x1800bfdc0  movzx   r8d, ax
0x1800bfdc4  or      r8d, edi
0x1800bfdc7  test    r8d, r8d
0x1800bfdca  js      short loc_1800BFE3A
0x1800bfdcc  mov     r9d, dword ptr [rbp+arg_0]
0x1800bfdd0  cmp     r9d, 14F0h
0x1800bfdd7  ja      short loc_1800BFE34
0x1800bfdd9  mov     rax, r15
0x1800bfddc  mul     r9
0x1800bfddf  shr     rdx, 9
0x1800bfde3  imul    rax, rdx, 218h
0x1800bfdea  cmp     r9, rax
0x1800bfded  jnz     short loc_1800BFE34
0x1800bfdef  test    r9d, r9d
0x1800bfdf2  jz      short loc_1800BFE3A
0x1800bfdf4  mov     rcx, [rbp+hkey]; hkey
0x1800bfdf8  lea     rax, [rbp+arg_0]
0x1800bfdfc  mov     [rsp+40h+pcbData], rax; pcbData
0x1800bfe01  lea     r8, aProfilehistory; "ProfileHistory"
0x1800bfe08  mov     rax, [rbx+30h]
0x1800bfe0c  mov     r9d, 20000008h; dwFlags
0x1800bfe12  mov     [rsp+40h+pvData], rax; pvData
0x1800bfe17  xor     edx, edx; lpSubKey
0x1800bfe19  mov     [rsp+40h+phkResult], rsi; pdwType
0x1800bfe1e  call    cs:__imp_RegGetValueW
0x1800bfe24  mov     r8d, eax
0x1800bfe27  test    eax, eax
0x1800bfe29  jle     short loc_1800BFE3A
0x1800bfe2b  movzx   r8d, ax
0x1800bfe2f  or      r8d, edi
0x1800bfe32  jmp     short loc_1800BFE3A
0x1800bfe34  mov     r8d, 8007000Dh
0x1800bfe3a  cmp     r8d, 80070002h
0x1800bfe41  mov     edi, esi
0x1800bfe43  cmovnz  edi, r8d
0x1800bfe47  test    edi, edi
0x1800bfe49  js      short loc_1800BFE85
0x1800bfe4b  mov     ecx, dword ptr [rbp+arg_0]
0x1800bfe4e  mov     rax, r15
0x1800bfe51  mul     rcx
0x1800bfe54  mov     r8d, esi
0x1800bfe57  shr     rdx, 9
0x1800bfe5b  mov     [rbx+38h], edx
0x1800bfe5e  test    edx, edx
0x1800bfe60  jle     short loc_1800BFE8A
0x1800bfe62  mov     rcx, [rbx+30h]
0x1800bfe66  movsxd  rax, r8d
0x1800bfe69  inc     r8d
0x1800bfe6c  imul    rdx, rax, 218h
0x1800bfe73  mov     [rdx+rcx+1FEh], si
0x1800bfe7b  mov     edx, [rbx+38h]
0x1800bfe7e  cmp     r8d, edx
0x1800bfe81  jl      short loc_1800BFE62
0x1800bfe83  jmp     short loc_1800BFE8A
0x1800bfe85  mov     [rbx+38h], esi
0x1800bfe88  mov     edx, esi
0x1800bfe8a  mov     eax, 0Ah
0x1800bfe8f  sub     eax, edx
0x1800bfe91  cdqe
0x1800bfe93  imul    r8, rax, 218h; Size
0x1800bfe9a  movsxd  rax, edx
0x1800bfe9d  xor     edx, edx; Val
0x1800bfe9f  imul    rcx, rax, 218h
0x1800bfea6  add     rcx, [rbx+30h]; void *
0x1800bfeaa  call    memset_0
0x1800bfeaf  mov     rcx, [rbp+hkey]; hKey
0x1800bfeb3  test    rcx, rcx
0x1800bfeb6  jz      short loc_1800BFEBE
0x1800bfeb8  call    cs:__imp_RegCloseKey
0x1800bfebe  mov     rcx, rbx; lpCriticalSection
0x1800bfec1  call    cs:__imp_LeaveCriticalSection
0x1800bfec7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfece  cmp     rcx, r12
0x1800bfed1  jz      short loc_1800BFEF1
0x1800bfed3  test    byte ptr [rcx+1Ch], 10h
0x1800bfed7  jz      short loc_1800BFEF1
0x1800bfed9  mov     rcx, [rcx+10h]
0x1800bfedd  lea     r8, WPP_59efe20e95083d54484ef368743a0c87_Traceguids
0x1800bfee4  mov     edx, 10h
0x1800bfee9  mov     r9d, edi
0x1800bfeec  call    WPP_SF_d
0x1800bfef1  mov     rbx, [rsp+40h+arg_18]
0x1800bfef9  mov     eax, edi
0x1800bfefb  add     rsp, 40h
0x1800bfeff  pop     r15
0x1800bff01  pop     r12
0x1800bff03  pop     rdi
0x1800bff04  pop     rsi
0x1800bff05  pop     rbp
0x1800bff06  retn
```
