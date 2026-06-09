# InstallLayoutOrTipPrivateHelpers::WriteKeyboardRegistry(CInputList &,bool,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &)

- ea: `0x180002344`
- end: `0x18000269e`
- name: `?WriteKeyboardRegistry@InstallLayoutOrTipPrivateHelpers@@SAXAEAVCInputList@@_NAEAVCInputDllRegKey@@22@Z`
- size: `858`
- prototype: `void __usercall(struct CInputList *@<rcx>, bool@<dl>, struct CInputDllRegKey *@<r8>, struct CInputDllRegKey *@<r9>, struct CInputDllRegKey *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180005500`

## callees

- `0x180002344`
- `0x1800026a4`
- `0x180002760`
- `0x180002820`
- `0x180004b70`
- `0x18004cb28`
- `0x18005030c`
- `0x18006c000`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000247a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800024de`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000253b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000262a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000247a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800024de`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000253b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000262a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000263e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000263e`
- `USER32!LoadKeyboardLayoutW` at `0x18000258d`
- `USER32!LoadKeyboardLayoutW` at `0x18000258d`

## pseudocode

```c
void __fastcall InstallLayoutOrTipPrivateHelpers::WriteKeyboardRegistry(
        struct CInputList *a1,
        char a2,
        struct CInputDllRegKey *a3,
        HKEY *a4,
        HKEY *a5)
{
  struct CInputDllRegKey *v5; // rsi
  HKEY *v8; // r15
  unsigned __int16 *v9; // rbx
  unsigned int v10; // r14d
  unsigned int v11; // r12d
  __int64 v12; // r9
  __int64 v13; // rax
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  const unsigned __int16 *v17; // rdx
  __int64 v18; // r9
  HKL KeyboardLayoutW; // rax
  char v20; // si
  unsigned int v21; // r15d
  __int64 v22; // rax
  BYTE Data[16]; // [rsp+48h] [rbp-39h] BYREF
  __int16 v26; // [rsp+58h] [rbp-29h]
  unsigned __int16 lpData[12]; // [rsp+60h] [rbp-21h] BYREF
  WCHAR ValueName[12]; // [rsp+78h] [rbp-9h] BYREF

  v5 = a3;
  v8 = a4;
  CInputDllRegKey::RecurseDeleteKey(a3, &sourceString, 0);
  CInputDllRegKey::RecurseDeleteKey((CInputDllRegKey *)v8, &sourceString, 0);
  if ( *(_DWORD *)a1 )
  {
    v9 = (unsigned __int16 *)*((_QWORD *)a1 + 1);
    if ( v9 )
    {
      v10 = 0;
      v11 = 1;
      do
      {
        if ( v10 >= *((_DWORD *)a1 + 1) )
          break;
        v12 = *((unsigned int *)v9 + 1);
        if ( (_DWORD)v12 )
        {
          if ( *((_BYTE *)v9 + 16) )
          {
            if ( (_DWORD)v12 != *v9 )
            {
              InstallLayoutOrTipPrivateHelpers::CalculateKeyboardSubstituteLayoutForEntry(
                v10,
                (struct InputContainer *)v9,
                a1);
              v12 = *((unsigned int *)v9 + 1);
            }
            if ( *((_DWORD *)v9 + 2) )
            {
              StringCchPrintfW((unsigned __int16 *)Data, 9u, L"%08x", *((unsigned int *)v9 + 2));
              StringCchPrintfW(ValueName, 0xAu, L"%d", v11);
              v13 = -1;
              do
                ++v13;
              while ( *(_WORD *)&Data[2 * v13] );
              RegSetValueExW(*((HKEY *)v5 + 1), ValueName, 0, 1u, Data, 2 * v13 + 2);
              InputTraceLoggingTelemetry::PreloadRegKeyChangedEvent(ValueName, v14, (const unsigned __int16 *)Data);
              StringCchPrintfW(lpData, 9u, L"%08x", *((unsigned int *)v9 + 1));
              v15 = -1;
              do
                ++v15;
              while ( lpData[v15] );
              RegSetValueExW(v8[1], (LPCWSTR)Data, 0, 1u, (const BYTE *)lpData, 2 * v15 + 2);
            }
            else
            {
              StringCchPrintfW((unsigned __int16 *)Data, 9u, L"%08x", v12);
              StringCchPrintfW(ValueName, 0xAu, L"%d", v11);
              v16 = -1;
              do
                ++v16;
              while ( *(_WORD *)&Data[2 * v16] );
              RegSetValueExW(*((HKEY *)v5 + 1), ValueName, 0, 1u, Data, 2 * v16 + 2);
              InputTraceLoggingTelemetry::PreloadRegKeyChangedEvent(ValueName, v17, (const unsigned __int16 *)Data);
            }
            if ( a2 )
            {
              v18 = *((unsigned int *)v9 + 2);
              v26 = 0;
              *(_OWORD *)Data = 0;
              if ( !(_DWORD)v18 )
                v18 = *((unsigned int *)v9 + 1);
              StringCchPrintfW((unsigned __int16 *)Data, 9u, L"%08x", v18);
              KeyboardLayoutW = LoadKeyboardLayoutW((LPCWSTR)Data, 0x82u);
              if ( v11 == 1 )
                InstallLayoutOrTipPrivateHelpers::SetDefaultKeyboard(KeyboardLayoutW);
            }
            ++v11;
          }
          if ( !*((_BYTE *)v9 + 18) || (v20 = 1, !*((_BYTE *)v9 + 16)) )
            v20 = 0;
          v21 = *((_DWORD *)v9 + 1);
          StringCchPrintfW((unsigned __int16 *)Data, 9u, L"%08x", *v9);
          if ( v20 )
          {
            StringCchPrintfW(lpData, 9u, L"%08x", v21);
            v22 = -1;
            do
              ++v22;
            while ( lpData[v22] );
            RegSetValueExW(a5[1], (LPCWSTR)Data, 0, 1u, (const BYTE *)lpData, 2 * v22 + 2);
          }
          else
          {
            RegDeleteValueW(a5[1], (LPCWSTR)Data);
          }
          v8 = a4;
          v5 = a3;
        }
        if ( ++v10 >= *(_DWORD *)a1 )
          break;
        v9 = (unsigned __int16 *)(*((_QWORD *)a1 + 1) + 700LL * v10);
      }
      while ( v9 );
    }
  }
  if ( a2 )
    InstallLayoutOrTipPrivateHelpers::UnloadKeyboards(a1);
}

```

## disassembly

```asm
0x180002344  mov     [rsp-8+arg_8], rbx
0x180002349  push    rbp
0x18000234a  push    rsi
0x18000234b  push    rdi
0x18000234c  push    r12
0x18000234e  push    r13
0x180002350  push    r14
0x180002352  push    r15
0x180002354  lea     rbp, [rsp-1Fh]
0x180002359  sub     rsp, 0A0h
0x180002360  mov     rax, cs:__security_cookie
0x180002367  xor     rax, rsp
0x18000236a  mov     [rbp+4Fh+var_40], rax
0x18000236e  mov     rax, [rbp+4Fh+arg_20]
0x180002372  mov     rsi, r8
0x180002375  mov     [rbp+4Fh+var_98], r8
0x180002379  mov     r13b, dl
0x18000237c  mov     rdi, rcx
0x18000237f  mov     [rbp+4Fh+var_90], r9
0x180002383  mov     rcx, rsi; this
0x180002386  mov     [rbp+4Fh+var_A0], rax
0x18000238a  xor     r8d, r8d; int
0x18000238d  lea     rdx, sourceString; unsigned __int16 *
0x180002394  mov     r15, r9
0x180002397  call    ?RecurseDeleteKey@CInputDllRegKey@@QEAAJPEBGH@Z; CInputDllRegKey::RecurseDeleteKey(ushort const *,int)
0x18000239c  xor     r8d, r8d; int
0x18000239f  lea     rdx, sourceString; unsigned __int16 *
0x1800023a6  mov     rcx, r15; this
0x1800023a9  call    ?RecurseDeleteKey@CInputDllRegKey@@QEAAJPEBGH@Z; CInputDllRegKey::RecurseDeleteKey(ushort const *,int)
0x1800023ae  xor     ecx, ecx
0x1800023b0  cmp     [rdi], ecx
0x1800023b2  jbe     loc_18000266A
0x1800023b8  mov     rbx, [rdi+8]
0x1800023bc  test    rbx, rbx
0x1800023bf  jz      loc_18000266A
0x1800023c5  mov     r14d, ecx
0x1800023c8  lea     r12d, [rcx+1]
0x1800023cc  cmp     r14d, [rdi+4]
0x1800023d0  jnb     loc_18000266A
0x1800023d6  mov     r9d, [rbx+4]
0x1800023da  test    r9d, r9d
0x1800023dd  jz      loc_18000264E
0x1800023e3  cmp     [rbx+10h], cl
0x1800023e6  jz      loc_1800025A6
0x1800023ec  movzx   eax, word ptr [rbx]
0x1800023ef  cmp     r9d, eax
0x1800023f2  jz      short loc_180002408
0x1800023f4  mov     r8, rdi; struct CInputList *
0x1800023f7  mov     rdx, rbx; struct InputContainer *
0x1800023fa  mov     ecx, r14d; unsigned int
0x1800023fd  call    ?CalculateKeyboardSubstituteLayoutForEntry@InstallLayoutOrTipPrivateHelpers@@SAXKPEAUInputContainer@@AEAVCInputList@@@Z; InstallLayoutOrTipPrivateHelpers::CalculateKeyboardSubstituteLayoutForEntry(ulong,InputContainer *,CInputList &)
0x180002402  mov     r9d, [rbx+4]
0x180002406  xor     ecx, ecx
0x180002408  cmp     [rbx+8], ecx
0x18000240b  lea     r8, a08x_1; "%08x"
0x180002412  lea     rcx, [rbp+4Fh+Data]; unsigned __int16 *
0x180002416  mov     edx, 9; unsigned __int64
0x18000241b  jz      loc_1800024E6
0x180002421  mov     r9d, [rbx+8]
0x180002425  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000242a  mov     r9d, r12d
0x18000242d  lea     r8, aD; "%d"
0x180002434  mov     edx, 0Ah; unsigned __int64
0x180002439  lea     rcx, [rbp+4Fh+ValueName]; unsigned __int16 *
0x18000243d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002442  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002446  lea     rdx, [rbp+4Fh+Data]
0x18000244a  xor     ecx, ecx
0x18000244c  inc     rax
0x18000244f  cmp     [rdx+rax*2], cx
0x180002453  jnz     short loc_18000244C
0x180002455  mov     rcx, [rsi+8]; hKey
0x180002459  lea     eax, ds:2[rax*2]
0x180002460  mov     [rsp+0D0h+cbData], eax; cbData
0x180002464  lea     rdx, [rbp+4Fh+ValueName]; lpValueName
0x180002468  lea     rax, [rbp+4Fh+Data]
0x18000246c  mov     r9d, 1; dwType
0x180002472  xor     r8d, r8d; Reserved
0x180002475  mov     [rsp+0D0h+lpData], rax; lpData
0x18000247a  call    cs:__imp_RegSetValueExW
0x180002480  lea     r8, [rbp+4Fh+Data]; unsigned __int16 *
0x180002484  lea     rcx, [rbp+4Fh+ValueName]; unsigned __int16 *
0x180002488  call    ?PreloadRegKeyChangedEvent@InputTraceLoggingTelemetry@@SAXPEBG00@Z; InputTraceLoggingTelemetry::PreloadRegKeyChangedEvent(ushort const *,ushort const *,ushort const *)
0x18000248d  mov     r9d, [rbx+4]
0x180002491  lea     r8, a08x_1; "%08x"
0x180002498  mov     edx, 9; unsigned __int64
0x18000249d  lea     rcx, [rbp+4Fh+var_70]; unsigned __int16 *
0x1800024a1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800024a6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800024aa  lea     rdx, [rbp+4Fh+var_70]
0x1800024ae  xor     ecx, ecx
0x1800024b0  inc     rax
0x1800024b3  cmp     [rdx+rax*2], cx
0x1800024b7  jnz     short loc_1800024B0
0x1800024b9  mov     rcx, [r15+8]; hKey
0x1800024bd  lea     eax, ds:2[rax*2]
0x1800024c4  mov     [rsp+0D0h+cbData], eax; cbData
0x1800024c8  lea     rdx, [rbp+4Fh+Data]; lpValueName
0x1800024cc  lea     rax, [rbp+4Fh+var_70]
0x1800024d0  mov     r9d, 1; dwType
0x1800024d6  xor     r8d, r8d; Reserved
0x1800024d9  mov     [rsp+0D0h+lpData], rax; lpData
0x1800024de  call    cs:__imp_RegSetValueExW
0x1800024e4  jmp     short loc_18000254E
0x1800024e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800024eb  mov     r9d, r12d
0x1800024ee  lea     r8, aD; "%d"
0x1800024f5  mov     edx, 0Ah; unsigned __int64
0x1800024fa  lea     rcx, [rbp+4Fh+ValueName]; unsigned __int16 *
0x1800024fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002503  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002507  lea     rdx, [rbp+4Fh+Data]
0x18000250b  xor     ecx, ecx
0x18000250d  inc     rax
0x180002510  cmp     [rdx+rax*2], cx
0x180002514  jnz     short loc_18000250D
0x180002516  mov     rcx, [rsi+8]; hKey
0x18000251a  lea     eax, ds:2[rax*2]
0x180002521  mov     [rsp+0D0h+cbData], eax; cbData
0x180002525  lea     rdx, [rbp+4Fh+ValueName]; lpValueName
0x180002529  lea     rax, [rbp+4Fh+Data]
0x18000252d  mov     r9d, 1; dwType
0x180002533  xor     r8d, r8d; Reserved
0x180002536  mov     [rsp+0D0h+lpData], rax; lpData
0x18000253b  call    cs:__imp_RegSetValueExW
0x180002541  lea     r8, [rbp+4Fh+Data]; unsigned __int16 *
0x180002545  lea     rcx, [rbp+4Fh+ValueName]; unsigned __int16 *
0x180002549  call    ?PreloadRegKeyChangedEvent@InputTraceLoggingTelemetry@@SAXPEBG00@Z; InputTraceLoggingTelemetry::PreloadRegKeyChangedEvent(ushort const *,ushort const *,ushort const *)
0x18000254e  xor     ecx, ecx
0x180002550  test    r13b, r13b
0x180002553  jz      short loc_1800025A3
0x180002555  mov     r9d, [rbx+8]
0x180002559  xor     eax, eax
0x18000255b  mov     [rbp+4Fh+var_78], ax
0x18000255f  xorps   xmm0, xmm0
0x180002562  movups  xmmword ptr [rbp+4Fh+Data], xmm0
0x180002566  test    r9d, r9d
0x180002569  jnz     short loc_18000256F
0x18000256b  mov     r9d, [rbx+4]
0x18000256f  lea     r8, a08x_1; "%08x"
0x180002576  mov     edx, 9; unsigned __int64
0x18000257b  lea     rcx, [rbp+4Fh+Data]; unsigned __int16 *
0x18000257f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002584  mov     edx, 82h; Flags
0x180002589  lea     rcx, [rbp+4Fh+Data]; pwszKLID
0x18000258d  call    cs:__imp_LoadKeyboardLayoutW
0x180002593  cmp     r12d, 1
0x180002597  jnz     short loc_1800025A1
0x180002599  mov     rcx, rax; HKL
0x18000259c  call    ?SetDefaultKeyboard@InstallLayoutOrTipPrivateHelpers@@SAXPEAUHKL__@@@Z; InstallLayoutOrTipPrivateHelpers::SetDefaultKeyboard(HKL__ *)
0x1800025a1  xor     ecx, ecx
0x1800025a3  inc     r12d
0x1800025a6  cmp     [rbx+12h], cl
0x1800025a9  jz      short loc_1800025B3
0x1800025ab  mov     sil, 1
0x1800025ae  cmp     [rbx+10h], cl
0x1800025b1  jnz     short loc_1800025B6
0x1800025b3  mov     sil, cl
0x1800025b6  movzx   r9d, word ptr [rbx]
0x1800025ba  lea     r8, a08x_1; "%08x"
0x1800025c1  mov     r15d, [rbx+4]
0x1800025c5  lea     rcx, [rbp+4Fh+Data]; unsigned __int16 *
0x1800025c9  mov     edx, 9; unsigned __int64
0x1800025ce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800025d3  xor     ebx, ebx
0x1800025d5  test    sil, sil
0x1800025d8  jz      short loc_180002632
0x1800025da  mov     r9d, r15d
0x1800025dd  lea     r8, a08x_1; "%08x"
0x1800025e4  lea     edx, [rbx+9]; unsigned __int64
0x1800025e7  lea     rcx, [rbp+4Fh+var_70]; unsigned __int16 *
0x1800025eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800025f0  lea     rcx, [rbp+4Fh+var_70]
0x1800025f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800025f8  inc     rax
0x1800025fb  cmp     [rcx+rax*2], bx
0x1800025ff  jnz     short loc_1800025F8
0x180002601  lea     eax, ds:2[rax*2]
0x180002608  mov     r9d, 1; dwType
0x18000260e  mov     [rsp+0D0h+cbData], eax; cbData
0x180002612  lea     rdx, [rbp+4Fh+Data]; lpValueName
0x180002616  lea     rax, [rbp+4Fh+var_70]
0x18000261a  xor     r8d, r8d; Reserved
0x18000261d  mov     [rsp+0D0h+lpData], rax; lpData
0x180002622  mov     rax, [rbp+4Fh+var_A0]
0x180002626  mov     rcx, [rax+8]; hKey
0x18000262a  call    cs:__imp_RegSetValueExW
0x180002630  jmp     short loc_180002644
0x180002632  mov     rax, [rbp+4Fh+var_A0]
0x180002636  lea     rdx, [rbp+4Fh+Data]; lpValueName
0x18000263a  mov     rcx, [rax+8]; hKey
0x18000263e  call    cs:__imp_RegDeleteValueW
0x180002644  mov     r15, [rbp+4Fh+var_90]
0x180002648  xor     ecx, ecx
0x18000264a  mov     rsi, [rbp+4Fh+var_98]
0x18000264e  inc     r14d
0x180002651  cmp     r14d, [rdi]
0x180002654  jnb     short loc_18000266A
0x180002656  mov     eax, r14d
0x180002659  imul    rbx, rax, 2BCh
0x180002660  add     rbx, [rdi+8]
0x180002664  jnz     loc_1800023CC
0x18000266a  test    r13b, r13b
0x18000266d  jz      short loc_180002677
0x18000266f  mov     rcx, rdi; struct CInputList *
0x180002672  call    ?UnloadKeyboards@InstallLayoutOrTipPrivateHelpers@@SAXAEAVCInputList@@@Z; InstallLayoutOrTipPrivateHelpers::UnloadKeyboards(CInputList &)
0x180002677  mov     rcx, [rbp+4Fh+var_40]
0x18000267b  xor     rcx, rsp; StackCookie
0x18000267e  call    __security_check_cookie
0x180002683  mov     rbx, [rsp+0D0h+arg_8]
0x18000268b  add     rsp, 0A0h
0x180002692  pop     r15
0x180002694  pop     r14
0x180002696  pop     r13
0x180002698  pop     r12
0x18000269a  pop     rdi
0x18000269b  pop     rsi
0x18000269c  pop     rbp
0x18000269d  retn
```
