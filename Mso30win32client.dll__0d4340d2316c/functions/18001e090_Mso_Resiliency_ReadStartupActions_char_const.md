# Mso::Resiliency::ReadStartupActions(char const *)

- ea: `0x18001e090`
- end: `0x18001e396`
- name: `?ReadStartupActions@Resiliency@Mso@@YAPEAU?$T_MSOPX@PEAUMSOSTARTUPACTION@@@Plex@DoNotUse@2@PEBD@Z`
- size: `774`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18001e090`
- `0x180020684`
- `0x180190750`
- `0x180468810`
- `0x180468978`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18001e2f5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18001e305`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18001e2f5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18001e305`
- `Mso20Win32Client!__imp_??IKey@Registry@Mso@@QEAAPEAPEAUHKEY__@@XZ` at `0x18001e0d4`
- `Mso20Win32Client!__imp_??IKey@Registry@Mso@@QEAAPEAPEAUHKEY__@@XZ` at `0x18001e0d4`
- `Mso20Win32Client!__imp_?MsoFreePx@@YAXPEAX@Z` at `0x18001e30f`
- `Mso20Win32Client!__imp_?MsoFreePx@@YAXPEAX@Z` at `0x18001e380`
- `Mso20Win32Client!__imp_?MsoFreePx@@YAXPEAX@Z` at `0x18001e30f`
- `Mso20Win32Client!__imp_?MsoFreePx@@YAXPEAX@Z` at `0x18001e380`
- `Mso20Win32Client!__imp_MsoFAllocPx` at `0x18001e182`
- `Mso20Win32Client!__imp_MsoFAllocPx` at `0x18001e182`
- `Mso20Win32Client!__imp_??1Key@Registry@Mso@@UEAA@XZ` at `0x18001e0fa`
- `Mso20Win32Client!__imp_??1Key@Registry@Mso@@UEAA@XZ` at `0x18001e2e2`
- `Mso20Win32Client!__imp_??1Key@Registry@Mso@@UEAA@XZ` at `0x18001e0fa`
- `Mso20Win32Client!__imp_??1Key@Registry@Mso@@UEAA@XZ` at `0x18001e2e2`
- `Mso20Win32Client!__imp_?MsoIAppendPx@@YAHPEAXPEBX@Z` at `0x18001e371`
- `Mso20Win32Client!__imp_?MsoIAppendPx@@YAHPEAXPEBX@Z` at `0x18001e371`
- `Mso20Win32Client!__imp_??BKey@Registry@Mso@@QEBAPEAUHKEY__@@XZ` at `0x18001e11d`
- `Mso20Win32Client!__imp_??BKey@Registry@Mso@@QEBAPEAUHKEY__@@XZ` at `0x18001e221`
- `Mso20Win32Client!__imp_??BKey@Registry@Mso@@QEBAPEAUHKEY__@@XZ` at `0x18001e265`
- `Mso20Win32Client!__imp_??BKey@Registry@Mso@@QEBAPEAUHKEY__@@XZ` at `0x18001e11d`
- `Mso20Win32Client!__imp_??BKey@Registry@Mso@@QEBAPEAUHKEY__@@XZ` at `0x18001e221`
- `Mso20Win32Client!__imp_??BKey@Registry@Mso@@QEBAPEAUHKEY__@@XZ` at `0x18001e265`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18001e1de`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18001e34b`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18001e1de`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18001e34b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18001e2cf`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18001e2d8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18001e32a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18001e338`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18001e38d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18001e2cf`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18001e2d8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18001e32a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18001e338`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18001e38d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001e162`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001e162`
- `ADVAPI32!RegEnumValueA` at `0x18001e24c`
- `ADVAPI32!RegEnumValueA` at `0x18001e24c`
- `ADVAPI32!RegDeleteValueA` at `0x18001e271`
- `ADVAPI32!RegDeleteValueA` at `0x18001e271`

## pseudocode

```c
void *__fastcall Mso::Resiliency::ReadStartupActions(LPCSTR lpSubKey)
{
  HKEY *v2; // rax
  HKEY v4; // rax
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rax
  unsigned int v7; // r8d
  DWORD *v8; // rax
  void *v9; // rdx
  Mso::Memory *v10; // rsi
  DWORD *v11; // rdi
  DWORD i; // r14d
  HKEY v13; // rax
  unsigned int v14; // r8d
  HKEY v15; // rax
  int v16; // eax
  __int64 v17; // rax
  void *v18; // rbx
  void *v19; // rdx
  void *v20; // rdx
  void *v21; // rax
  void *v22; // rdx
  DWORD cbData; // [rsp+60h] [rbp-9h] BYREF
  DWORD cchValueName[2]; // [rsp+68h] [rbp-1h] BYREF
  void *v25; // [rsp+70h] [rbp+7h] BYREF
  void *v26; // [rsp+78h] [rbp+Fh] BYREF
  void **v27; // [rsp+80h] [rbp+17h] BYREF
  int v28; // [rsp+88h] [rbp+1Fh]
  __int64 v29; // [rsp+90h] [rbp+27h]
  char v30; // [rsp+98h] [rbp+2Fh]
  DWORD cbMaxValueLen; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD cValues; // [rsp+E0h] [rbp+77h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+E8h] [rbp+7Fh] BYREF

  v28 = 1;
  v29 = 0;
  cValues = 0;
  v27 = &Mso::Registry::Key::`vftable';
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v30 = 1;
  v2 = (HKEY *)Mso::Registry::Key::operator&(&v27);
  if ( !(unsigned int)MsoRegOpenKeyExA(HKEY_CURRENT_USER, lpSubKey, 0x3001Fu, v2) )
  {
    v4 = (HKEY)Mso::Registry::Key::operator HKEY__ *(&v27);
    RegQueryInfoKeyW(v4, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
    if ( cValues )
    {
      v25 = 0;
      if ( (unsigned int)MsoFAllocPx(&v25, 8, 1) )
      {
        if ( (unsigned __int64)cbMaxValueLen + 4 > 0xFFFFFFFF
          || (cbMaxValueLen += 4, v5 = cbMaxValueNameLen + 4LL, v5 > 0xFFFFFFFF)
          || (cbMaxValueNameLen += 4, v6 = (unsigned int)v5 + 1LL, *(_QWORD *)cchValueName = 0, v6 > 0xFFFFFFFF) )
        {
          __fastfail(5u);
        }
        Mso::MemoryPtr<_GUID,0>::AllocBytes(cchValueName, (unsigned int)v6);
        v8 = (DWORD *)Mso::Memory::AllocateEx((Mso::Memory *)cbMaxValueLen, 0, v7);
        v10 = *(Mso::Memory **)cchValueName;
        v11 = 0;
        if ( v8 )
          v11 = v8;
        if ( *(_QWORD *)cchValueName && v11 )
        {
          for ( i = 0; ; ++i )
          {
            if ( i >= cValues )
            {
              v18 = v25;
              Mso::Memory::Free((Mso::Memory *)v11, v9);
              Mso::Memory::Free(v10, v19);
              Mso::Registry::Key::~Key((Mso::Registry::Key *)&v27);
              return v18;
            }
            cchValueName[0] = cbMaxValueNameLen;
            cbData = cbMaxValueLen;
            v13 = (HKEY)Mso::Registry::Key::operator HKEY__ *(&v27);
            if ( !RegEnumValueA(v13, i, (LPSTR)v10, cchValueName, 0, 0, (LPBYTE)v11, &cbData) )
            {
              v9 = (void *)cbData;
              LOBYTE(v14) = 0;
              if ( cbData < 0x1C )
                goto LABEL_16;
              if ( cbData == v11[6] + 28LL )
              {
                v16 = FProcessAlive(v11[1]);
                v9 = (void *)cbData;
                LOBYTE(v14) = v16 != 0;
              }
              if ( (unsigned int)v9 < 0x1C )
                goto LABEL_16;
              v17 = v11[6] + 28LL;
              if ( (unsigned int)v9 != v17 )
                goto LABEL_16;
              if ( !(_BYTE)v14 )
                break;
            }
LABEL_22:
            ;
          }
          if ( (unsigned int)v9 == v17 )
          {
            v21 = Mso::Memory::AllocateEx((Mso::Memory *)(unsigned int)v9, 0, v14);
            v26 = v21;
            if ( !v21 )
            {
              MsoFreePx(v25);
              v25 = 0;
              Mso::Memory::Free((Mso::Memory *)v11, v22);
              goto LABEL_29;
            }
            memcpy_0(v21, v11, cbData);
            MsoIAppendPx(v25, &v26);
          }
LABEL_16:
          v15 = (HKEY)Mso::Registry::Key::operator HKEY__ *(&v27);
          RegDeleteValueA(v15, (LPCSTR)v10);
          --cValues;
          i = -1;
          goto LABEL_22;
        }
        MsoShipAssertTagProc(539254869);
        MsoFreePx(v25);
        v25 = 0;
        if ( v11 )
          Mso::Memory::Free((Mso::Memory *)v11, v20);
        if ( v10 )
LABEL_29:
          Mso::Memory::Free(v10, v20);
      }
      else
      {
        MsoShipAssertTagProc(539254870);
      }
    }
  }
  Mso::Registry::Key::~Key((Mso::Registry::Key *)&v27);
  return 0;
}

```

## disassembly

```asm
0x18001e090  mov     [rsp-8+arg_0], rbx
0x18001e095  push    rbp
0x18001e096  push    rsi
0x18001e097  push    rdi
0x18001e098  push    r14
0x18001e09a  push    r15
0x18001e09c  lea     rbp, [rsp-37h]
0x18001e0a1  sub     rsp, 0A0h
0x18001e0a8  xor     ebx, ebx
0x18001e0aa  mov     [rbp+57h+var_38], 1
0x18001e0b1  mov     rdi, rcx
0x18001e0b4  mov     [rbp+57h+var_30], rbx
0x18001e0b8  lea     rax, ??_7Key@Registry@Mso@@6B@; const Mso::Registry::Key::`vftable'
0x18001e0bf  mov     [rbp+57h+cValues], ebx
0x18001e0c2  lea     rcx, [rbp+57h+var_40]
0x18001e0c6  mov     [rbp+57h+var_40], rax
0x18001e0ca  mov     [rbp+57h+cbMaxValueNameLen], ebx
0x18001e0cd  mov     [rbp+57h+cbMaxValueLen], ebx
0x18001e0d0  mov     [rbp+57h+var_28], 1
0x18001e0d4  call    cs:__imp_??IKey@Registry@Mso@@QEAAPEAPEAUHKEY__@@XZ; Mso::Registry::Key::operator&(void)
0x18001e0da  mov     r8d, 3001Fh; unsigned int
0x18001e0e0  mov     rdx, rdi; lpSubKey
0x18001e0e3  mov     r9, rax; HKEY *
0x18001e0e6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001e0ed  call    ?MsoRegOpenKeyExA@@YAJPEAUHKEY__@@PEBDKPEAPEAU1@@Z; MsoRegOpenKeyExA(HKEY__ *,char const *,ulong,HKEY__ * *)
0x18001e0f2  test    eax, eax
0x18001e0f4  jz      short loc_18001E119
0x18001e0f6  lea     rcx, [rbp+57h+var_40]
0x18001e0fa  call    cs:__imp_??1Key@Registry@Mso@@UEAA@XZ; Mso::Registry::Key::~Key(void)
0x18001e100  xor     eax, eax
0x18001e102  mov     rbx, [rsp+0C0h+arg_0]
0x18001e10a  add     rsp, 0A0h
0x18001e111  pop     r15
0x18001e113  pop     r14
0x18001e115  pop     rdi
0x18001e116  pop     rsi
0x18001e117  pop     rbp
0x18001e118  retn
0x18001e119  lea     rcx, [rbp+57h+var_40]
0x18001e11d  call    cs:__imp_??BKey@Registry@Mso@@QEBAPEAUHKEY__@@XZ; Mso::Registry::Key::operator HKEY__ *(void)
0x18001e123  mov     [rsp+0C0h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18001e128  lea     rcx, [rbp+57h+cbMaxValueLen]
0x18001e12c  mov     [rsp+0C0h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18001e131  xor     r9d, r9d; lpReserved
0x18001e134  mov     [rsp+0C0h+lpcbMaxValueLen], rcx; lpcbMaxValueLen
0x18001e139  xor     r8d, r8d; lpcchClass
0x18001e13c  lea     rcx, [rbp+57h+cbMaxValueNameLen]
0x18001e140  xor     edx, edx; lpClass
0x18001e142  mov     [rsp+0C0h+lpcbMaxValueNameLen], rcx; lpcbMaxValueNameLen
0x18001e147  lea     rcx, [rbp+57h+cValues]
0x18001e14b  mov     [rsp+0C0h+lpcValues], rcx; lpcValues
0x18001e150  mov     rcx, rax; hKey
0x18001e153  mov     [rsp+0C0h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x18001e158  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rbx; lpcbMaxSubKeyLen
0x18001e15d  mov     [rsp+0C0h+lpcSubKeys], rbx; lpcSubKeys
0x18001e162  call    cs:__imp_RegQueryInfoKeyW
0x18001e168  mov     r9d, [rbp+57h+cValues]
0x18001e16c  test    r9d, r9d
0x18001e16f  jz      short loc_18001E0F6
0x18001e171  mov     edx, 8
0x18001e176  mov     [rbp+57h+var_50], rbx
0x18001e17a  lea     rcx, [rbp+57h+var_50]
0x18001e17e  lea     r8d, [rdx-7]
0x18001e182  call    cs:__imp_MsoFAllocPx
0x18001e188  test    eax, eax
0x18001e18a  jz      loc_18001E2F0
0x18001e190  mov     eax, [rbp+57h+cbMaxValueLen]
0x18001e193  mov     r15d, 0FFFFFFFFh
0x18001e199  add     rax, 4
0x18001e19d  cmp     rax, r15
0x18001e1a0  ja      loc_18001E2C1
0x18001e1a6  mov     [rbp+57h+cbMaxValueLen], eax
0x18001e1a9  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18001e1ac  add     rax, 4
0x18001e1b0  cmp     rax, r15
0x18001e1b3  ja      loc_18001E2C1
0x18001e1b9  mov     eax, eax
0x18001e1bb  mov     [rbp+57h+cbMaxValueNameLen], eax
0x18001e1be  inc     rax
0x18001e1c1  mov     qword ptr [rbp+57h+cchValueName], rbx
0x18001e1c5  cmp     rax, r15
0x18001e1c8  ja      loc_18001E2C1
0x18001e1ce  mov     edx, eax
0x18001e1d0  lea     rcx, [rbp+57h+cchValueName]
0x18001e1d4  call    ?AllocBytes@?$MemoryPtr@U_GUID@@$0A@@Mso@@QEAA_N_K@Z; Mso::MemoryPtr<_GUID,0>::AllocBytes(unsigned __int64)
0x18001e1d9  mov     ecx, [rbp+57h+cbMaxValueLen]
0x18001e1dc  xor     edx, edx
0x18001e1de  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18001e1e4  mov     rsi, qword ptr [rbp+57h+cchValueName]
0x18001e1e8  mov     rdi, rbx
0x18001e1eb  test    rax, rax
0x18001e1ee  cmovnz  rdi, rax
0x18001e1f2  test    rsi, rsi
0x18001e1f5  jz      loc_18001E300
0x18001e1fb  test    rdi, rdi
0x18001e1fe  jz      loc_18001E300
0x18001e204  mov     r14d, ebx
0x18001e207  cmp     r14d, [rbp+57h+cValues]
0x18001e20b  jnb     loc_18001E2C8
0x18001e211  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18001e214  lea     rcx, [rbp+57h+var_40]
0x18001e218  mov     [rbp+57h+cchValueName], eax
0x18001e21b  mov     eax, [rbp+57h+cbMaxValueLen]
0x18001e21e  mov     [rbp+57h+cbData], eax
0x18001e221  call    cs:__imp_??BKey@Registry@Mso@@QEBAPEAUHKEY__@@XZ; Mso::Registry::Key::operator HKEY__ *(void)
0x18001e227  lea     rcx, [rbp+57h+cbData]
0x18001e22b  mov     r8, rsi; lpValueName
0x18001e22e  mov     [rsp+0C0h+lpcValues], rcx; lpcbData
0x18001e233  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18001e237  mov     [rsp+0C0h+lpcbMaxClassLen], rdi; lpData
0x18001e23c  mov     edx, r14d; dwIndex
0x18001e23f  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rbx; lpType
0x18001e244  mov     rcx, rax; hKey
0x18001e247  mov     [rsp+0C0h+lpcSubKeys], rbx; lpReserved
0x18001e24c  call    cs:__imp_RegEnumValueA
0x18001e252  test    eax, eax
0x18001e254  jnz     short loc_18001E2B9
0x18001e256  mov     edx, [rbp+57h+cbData]
0x18001e259  mov     r8b, bl
0x18001e25c  cmp     edx, 1Ch
0x18001e25f  jnb     short loc_18001E280
0x18001e261  lea     rcx, [rbp+57h+var_40]
0x18001e265  call    cs:__imp_??BKey@Registry@Mso@@QEBAPEAUHKEY__@@XZ; Mso::Registry::Key::operator HKEY__ *(void)
0x18001e26b  mov     rcx, rax; hKey
0x18001e26e  mov     rdx, rsi; lpValueName
0x18001e271  call    cs:__imp_RegDeleteValueA
0x18001e277  add     [rbp+57h+cValues], r15d
0x18001e27b  mov     r14d, r15d
0x18001e27e  jmp     short loc_18001E2B9
0x18001e280  mov     ecx, [rdi+18h]
0x18001e283  add     rcx, 1Ch
0x18001e287  cmp     rdx, rcx
0x18001e28a  jnz     short loc_18001E29D
0x18001e28c  mov     ecx, [rdi+4]; dwProcessId
0x18001e28f  call    ?FProcessAlive@@YAHK@Z; FProcessAlive(ulong)
0x18001e294  mov     edx, [rbp+57h+cbData]
0x18001e297  test    eax, eax
0x18001e299  setnz   r8b
0x18001e29d  cmp     edx, 1Ch
0x18001e2a0  jb      short loc_18001E261
0x18001e2a2  mov     eax, [rdi+18h]
0x18001e2a5  add     rax, 1Ch
0x18001e2a9  mov     ecx, edx
0x18001e2ab  cmp     rcx, rax
0x18001e2ae  jnz     short loc_18001E261
0x18001e2b0  test    r8b, r8b
0x18001e2b3  jz      loc_18001E340
0x18001e2b9  inc     r14d
0x18001e2bc  jmp     loc_18001E207
0x18001e2c1  mov     ecx, 5
0x18001e2c6  int     29h; Win8: RtlFailFast(ecx)
0x18001e2c8  mov     rbx, [rbp+57h+var_50]
0x18001e2cc  mov     rcx, rdi
0x18001e2cf  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18001e2d5  mov     rcx, rsi
0x18001e2d8  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18001e2de  lea     rcx, [rbp+57h+var_40]
0x18001e2e2  call    cs:__imp_??1Key@Registry@Mso@@UEAA@XZ; Mso::Registry::Key::~Key(void)
0x18001e2e8  mov     rax, rbx
0x18001e2eb  jmp     loc_18001E102
0x18001e2f0  mov     ecx, 20246056h
0x18001e2f5  call    cs:__imp_MsoShipAssertTagProc
0x18001e2fb  jmp     loc_18001E0F6
0x18001e300  mov     ecx, 20246055h
0x18001e305  call    cs:__imp_MsoShipAssertTagProc
0x18001e30b  mov     rcx, [rbp+57h+var_50]
0x18001e30f  call    cs:__imp_?MsoFreePx@@YAXPEAX@Z; MsoFreePx(void *)
0x18001e315  mov     [rbp+57h+var_50], rbx
0x18001e319  test    rdi, rdi
0x18001e31c  jnz     short loc_18001E335
0x18001e31e  test    rsi, rsi
0x18001e321  jz      loc_18001E0F6
0x18001e327  mov     rcx, rsi
0x18001e32a  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18001e330  jmp     loc_18001E0F6
0x18001e335  mov     rcx, rdi
0x18001e338  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18001e33e  jmp     short loc_18001E31E
0x18001e340  cmp     rcx, rax
0x18001e343  jnz     loc_18001E261
0x18001e349  xor     edx, edx
0x18001e34b  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18001e351  mov     [rbp+57h+var_48], rax
0x18001e355  test    rax, rax
0x18001e358  jz      short loc_18001E37C
0x18001e35a  mov     r8d, [rbp+57h+cbData]; Size
0x18001e35e  mov     rdx, rdi; Src
0x18001e361  mov     rcx, rax; void *
0x18001e364  call    memcpy_0
0x18001e369  mov     rcx, [rbp+57h+var_50]
0x18001e36d  lea     rdx, [rbp+57h+var_48]
0x18001e371  call    cs:__imp_?MsoIAppendPx@@YAHPEAXPEBX@Z; MsoIAppendPx(void *,void const *)
0x18001e377  jmp     loc_18001E261
0x18001e37c  mov     rcx, [rbp+57h+var_50]
0x18001e380  call    cs:__imp_?MsoFreePx@@YAXPEAX@Z; MsoFreePx(void *)
0x18001e386  mov     rcx, rdi
0x18001e389  mov     [rbp+57h+var_50], rbx
0x18001e38d  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18001e393  jmp     short loc_18001E327
```
