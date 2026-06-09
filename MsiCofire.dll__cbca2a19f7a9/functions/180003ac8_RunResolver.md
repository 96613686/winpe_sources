# RunResolver

- ea: `0x180003ac8`
- end: `0x180003ff0`
- name: `RunResolver`
- size: `1320`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180002770`

## callees

- `0x180002590`
- `0x180002f08`
- `0x1800035f4`
- `0x180003ac8`
- `0x1800043d8`
- `0x180004a70`
- `0x180004f1c`
- `0x180004fa0`
- `0x180005020`
- `0x18000595c`
- `0x180005b1c`
- `0x180005b78`
- `0x180005bd4`
- `0x180006530`
- `0x180007013`
- `0x180007040`
- `0x180008010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180003e45`
- `KERNEL32!GetTickCount64` at `0x180003e85`
- `KERNEL32!GetTickCount64` at `0x180003e45`
- `KERNEL32!GetTickCount64` at `0x180003e85`
- `KERNEL32!GetLastError` at `0x180003f46`
- `KERNEL32!GetLastError` at `0x180003f46`
- `KERNEL32!HeapAlloc` at `0x180003c3b`
- `KERNEL32!HeapAlloc` at `0x180003d15`
- `KERNEL32!HeapAlloc` at `0x180003c3b`
- `KERNEL32!HeapAlloc` at `0x180003d15`
- `KERNEL32!GetProcAddress` at `0x180003ed2`
- `KERNEL32!GetProcAddress` at `0x180003ed2`
- `KERNEL32!FreeLibrary` at `0x180003f8f`
- `KERNEL32!FreeLibrary` at `0x180003f8f`
- `KERNEL32!GetProcessHeap` at `0x180003c2d`
- `KERNEL32!GetProcessHeap` at `0x180003d07`
- `KERNEL32!GetProcessHeap` at `0x180003c2d`
- `KERNEL32!GetProcessHeap` at `0x180003d07`

## string_xrefs

- `0x180003f6e`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`
- `0x180003af8`: `Software\Microsoft\Windows NT\CurrentVersion\MsiCorruptedFileRecovery\RepairedProducts`
- `0x180003ec8`: `MsiReinstallProductW`

## pseudocode

```c
__int64 __fastcall RunResolver(void *a1)
{
  unsigned int v2; // edi
  int v3; // eax
  signed int v4; // ebx
  HMODULE ModFromSystem; // r15
  int MsiComponentAndProduct; // eax
  __int64 v7; // rsi
  __int64 v8; // rbx
  HANDLE ProcessHeap; // rax
  _WORD *v10; // r8
  __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  __int64 v13; // r14
  unsigned __int16 *v14; // rcx
  __int64 v15; // rax
  _WORD *v16; // rcx
  __int64 v17; // rbx
  HANDLE v18; // rax
  _WORD *v19; // r8
  unsigned __int64 v20; // rdx
  signed int v21; // ecx
  unsigned __int16 *v22; // rax
  _WORD *v23; // rcx
  int v24; // eax
  int v25; // eax
  int GroupPolicySetting; // eax
  ULONGLONG TickCount64; // rsi
  int v28; // eax
  ULONGLONG v29; // rax
  FARPROC ProcAddress; // rax
  int v31; // r9d
  int v32; // eax
  signed int LastError; // eax
  int pnButton; // [rsp+40h] [rbp-C0h] BYREF
  int v36; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v38; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v39; // [rsp+60h] [rbp-A0h]
  __int64 v40; // [rsp+68h] [rbp-98h]
  int v41; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v42[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v43; // [rsp+88h] [rbp-78h]
  __int64 v44; // [rsp+90h] [rbp-70h]
  int v45; // [rsp+98h] [rbp-68h]
  _BYTE v46[32]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR v47[40]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v48[80]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v49[264]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v50[264]; // [rsp+370h] [rbp+270h] BYREF

  v2 = 5;
  Throttler::Throttler(
    (Throttler *)v46,
    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\MsiCorruptedFileRecovery\\RepairedProducts",
    1);
  v39 = 0;
  v40 = 0;
  v38 = 0;
  v41 = 0;
  *(_OWORD *)v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v3 = CrashEventData::LoadFromWdi((CrashEventData *)v42, a1);
  v4 = v3;
  if ( v3 < 0 )
  {
    ModFromSystem = 0;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "RunResolver", 414, v3);
    goto LABEL_72;
  }
  ModFromSystem = LoadModFromSystem();
  if ( (unsigned __int64)ModFromSystem - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v31 = 417;
    goto LABEL_71;
  }
  v37 = 0x10400000104LL;
  memset_0(v49, 0, 0x208u);
  MsiComponentAndProduct = GetMsiComponentAndProduct(
                             ModFromSystem,
                             v42[0],
                             (__int64)v47,
                             (__int64)v48,
                             (__int64)v50,
                             (__int64)&v37 + 4,
                             (__int64)v49,
                             (__int64)&v37);
  v4 = MsiComponentAndProduct;
  if ( MsiComponentAndProduct == -2147023728 )
  {
    v4 = 0;
    v2 = g_bDmCanceled != 0 ? 18 : 15;
    HIDWORD(v40) = v2;
    goto LABEL_72;
  }
  if ( MsiComponentAndProduct < 0 )
  {
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "RunResolver", 434, MsiComponentAndProduct);
    goto LABEL_72;
  }
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( v50[v8] );
  ProcessHeap = GetProcessHeap();
  *(_QWORD *)&v38 = HeapAlloc(ProcessHeap, 0, 2 * v8 + 2);
  v10 = (_WORD *)v38;
  if ( !(_QWORD)v38 )
  {
    v4 = -2147024882;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "RunResolver", 440, -2147024882);
    goto LABEL_72;
  }
  v11 = -1;
  do
    ++v11;
  while ( v50[v11] );
  v12 = v11 + 1;
  if ( !v12 )
  {
    v4 = -2147024809;
    goto LABEL_67;
  }
  if ( v12 > 0x7FFFFFFF )
  {
    v4 = -2147024809;
    *(_WORD *)v38 = 0;
LABEL_67:
    v31 = 442;
    goto LABEL_71;
  }
  v13 = 2147483646;
  v14 = v50;
  v15 = 2147483646;
  do
  {
    if ( !v15 )
      break;
    if ( !*v14 )
      break;
    *v10++ = *v14++;
    --v15;
    --v12;
  }
  while ( v12 );
  v16 = v10 - 1;
  v4 = v12 == 0 ? 0x8007007A : 0;
  if ( v12 )
    v16 = v10;
  *v16 = 0;
  if ( !v12 )
    goto LABEL_67;
  v17 = -1;
  do
    ++v17;
  while ( v49[v17] );
  v18 = GetProcessHeap();
  *((_QWORD *)&v38 + 1) = HeapAlloc(v18, 0, 2 * v17 + 2);
  v19 = (_WORD *)*((_QWORD *)&v38 + 1);
  if ( !*((_QWORD *)&v38 + 1) )
  {
    v4 = -2147024882;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "RunResolver", 444, -2147024882);
    goto LABEL_72;
  }
  do
    ++v7;
  while ( v49[v7] );
  v20 = v7 + 1;
  if ( v7 == -1 )
  {
    v21 = -2147024809;
  }
  else
  {
    if ( v20 > 0x7FFFFFFF )
    {
      v4 = -2147024809;
      v21 = -2147024809;
      **((_WORD **)&v38 + 1) = 0;
      goto LABEL_40;
    }
    v22 = v49;
    do
    {
      if ( !v13 )
        break;
      if ( !*v22 )
        break;
      *v19++ = *v22++;
      --v13;
      --v20;
    }
    while ( v20 );
    v23 = v19 - 1;
    if ( v20 )
      v23 = v19;
    *v23 = 0;
    v21 = v20 == 0 ? 0x8007007A : 0;
  }
  v4 = v21;
  if ( v21 < 0 )
  {
LABEL_40:
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "RunResolver", 446, v21);
    goto LABEL_72;
  }
  v24 = Throttler::ProcessOccurrence((Throttler *)v46, v47);
  if ( v24 )
  {
    v25 = v24 - 1;
    if ( v25 )
    {
      if ( v25 == 1 )
        v2 = 11;
      else
        v2 = 8;
    }
    else
    {
      v2 = 12;
    }
    goto LABEL_72;
  }
  v36 = 2;
  GroupPolicySetting = GetGroupPolicySetting(&v36);
  v4 = GroupPolicySetting;
  if ( GroupPolicySetting < 0 )
  {
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "RunResolver", 480, GroupPolicySetting);
    goto LABEL_72;
  }
  if ( v36 != 2 )
  {
    v2 = 20;
LABEL_53:
    HIDWORD(v40) = v2;
    goto LABEL_72;
  }
  pnButton = 7;
  TickCount64 = GetTickCount64();
  v28 = ShowReinstallUI(v42[0], v50, v49, &pnButton);
  v4 = v28;
  if ( v28 < 0 )
  {
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "RunResolver", 496, v28);
    goto LABEL_72;
  }
  v29 = GetTickCount64();
  LODWORD(v40) = (pnButton != 6) + 1;
  v39 = (v29 - TickCount64) / 0x3E8;
  if ( pnButton != 6 )
  {
    v2 = 18;
    goto LABEL_53;
  }
  ProcAddress = GetProcAddress(ModFromSystem, "MsiReinstallProductW");
  if ( !ProcAddress )
  {
    v4 = -2147467259;
    v31 = 512;
LABEL_71:
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "RunResolver", v31, v4);
    goto LABEL_72;
  }
  v32 = ((__int64 (__fastcall *)(WCHAR *, __int64))ProcAddress)(v47, 64);
  if ( v32 > 0 )
    v4 = (unsigned __int16)v32 | 0x80070000;
  else
    v4 = v32;
  if ( v4 >= 0 )
  {
    HIDWORD(v40) = 16;
  }
  else
  {
    v2 = 17;
    v41 = v32;
    HIDWORD(v40) = 17;
  }
LABEL_72:
  ResolverData::StoreInWdi((ResolverData *)&v38, a1);
  if ( ModFromSystem )
    FreeLibrary(ModFromSystem);
  if ( v4 < 0 && v2 == 5 )
    v2 = 4;
  SetScenarioResultParameter(a1, v2);
  SetScenarioDMError(a1, (unsigned int)v4);
  CrashEventData::Free((CrashEventData *)v42);
  ResolverData::Free((ResolverData *)&v38);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003ac8  push    rbp
0x180003aca  push    rbx
0x180003acb  push    rsi
0x180003acc  push    rdi
0x180003acd  push    r12
0x180003acf  push    r13
0x180003ad1  push    r14
0x180003ad3  push    r15
0x180003ad5  lea     rbp, [rsp-498h]
0x180003add  sub     rsp, 598h
0x180003ae4  mov     rax, cs:__security_cookie
0x180003aeb  xor     rax, rsp
0x180003aee  mov     [rbp+4D0h+var_50], rax
0x180003af5  mov     r12, rcx
0x180003af8  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x180003aff  mov     edi, 5
0x180003b04  lea     rcx, [rbp+4D0h+var_530]; this
0x180003b08  lea     r8d, [rdi-4]; int
0x180003b0c  call    ??0Throttler@@QEAA@PEBGH@Z; Throttler::Throttler(ushort const *,int)
0x180003b11  xor     r13d, r13d
0x180003b14  lea     rcx, [rsp+5D0h+var_558]; this
0x180003b19  xorps   xmm0, xmm0
0x180003b1c  mov     [rsp+5D0h+var_570], r13
0x180003b21  mov     rdx, r12; void *
0x180003b24  mov     [rsp+5D0h+var_568], r13
0x180003b29  movdqu  [rsp+5D0h+var_580], xmm0
0x180003b2f  mov     [rsp+5D0h+var_560], r13d
0x180003b34  movdqu  xmmword ptr [rsp+5D0h+var_558], xmm0
0x180003b3a  mov     [rbp+4D0h+var_548], r13
0x180003b3e  mov     [rbp+4D0h+var_540], r13
0x180003b42  mov     [rbp+4D0h+var_538], r13d
0x180003b46  call    ?LoadFromWdi@CrashEventData@@QEAAJPEAX@Z; CrashEventData::LoadFromWdi(void *)
0x180003b4b  mov     ebx, eax
0x180003b4d  test    eax, eax
0x180003b4f  jns     short loc_180003B63
0x180003b51  mov     r15d, r13d
0x180003b54  mov     dword ptr [rsp+5D0h+var_5B0], eax
0x180003b58  mov     r9d, 19Eh
0x180003b5e  jmp     loc_180003F65
0x180003b63  call    LoadModFromSystem
0x180003b68  mov     r15, rax
0x180003b6b  lea     rcx, [rax-1]
0x180003b6f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180003b73  ja      loc_180003F46
0x180003b79  mov     eax, 104h
0x180003b7e  lea     rcx, [rbp+4D0h+var_470]; void *
0x180003b82  xor     edx, edx; Val
0x180003b84  mov     dword ptr [rsp+5D0h+var_588+4], eax
0x180003b88  mov     r8d, 208h; Size
0x180003b8e  mov     dword ptr [rsp+5D0h+var_588], eax
0x180003b92  call    memset_0
0x180003b97  mov     rdx, [rsp+5D0h+var_558]
0x180003b9c  lea     rax, [rsp+5D0h+var_588]
0x180003ba1  mov     [rsp+5D0h+var_598], rax; __int64
0x180003ba6  lea     r9, [rbp+4D0h+var_4C0]
0x180003baa  lea     rax, [rbp+4D0h+var_470]
0x180003bae  mov     rcx, r15; hModule
0x180003bb1  mov     [rsp+5D0h+var_5A0], rax; __int64
0x180003bb6  lea     r8, [rbp+4D0h+var_510]
0x180003bba  lea     rax, [rsp+5D0h+var_588+4]
0x180003bbf  mov     [rsp+5D0h+var_5A8], rax; __int64
0x180003bc4  lea     rax, [rbp+4D0h+var_260]
0x180003bcb  mov     [rsp+5D0h+var_5B0], rax; __int64
0x180003bd0  call    GetMsiComponentAndProduct
0x180003bd5  mov     ebx, eax
0x180003bd7  cmp     eax, 80070490h
0x180003bdc  jnz     short loc_180003BFA
0x180003bde  mov     eax, cs:g_bDmCanceled
0x180003be4  mov     ebx, r13d
0x180003be7  neg     eax
0x180003be9  sbb     edi, edi
0x180003beb  and     edi, 3
0x180003bee  add     edi, 0Fh
0x180003bf1  mov     dword ptr [rsp+5D0h+var_568+4], edi
0x180003bf5  jmp     loc_180003F7A
0x180003bfa  test    eax, eax
0x180003bfc  jns     short loc_180003C0D
0x180003bfe  mov     dword ptr [rsp+5D0h+var_5B0], eax
0x180003c02  mov     r9d, 1B2h
0x180003c08  jmp     loc_180003F65
0x180003c0d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003c11  lea     rax, [rbp+4D0h+var_260]
0x180003c18  mov     rbx, rsi
0x180003c1b  inc     rbx
0x180003c1e  cmp     [rax+rbx*2], r13w
0x180003c23  jnz     short loc_180003C1B
0x180003c25  lea     rbx, ds:2[rbx*2]
0x180003c2d  call    cs:__imp_GetProcessHeap
0x180003c33  mov     r8, rbx; dwBytes
0x180003c36  xor     edx, edx; dwFlags
0x180003c38  mov     rcx, rax; hHeap
0x180003c3b  call    cs:__imp_HeapAlloc
0x180003c41  mov     qword ptr [rsp+5D0h+var_580], rax
0x180003c46  mov     r8, rax
0x180003c49  test    rax, rax
0x180003c4c  jnz     short loc_180003C64
0x180003c4e  mov     eax, 8007000Eh
0x180003c53  mov     r9d, 1B8h
0x180003c59  mov     ebx, eax
0x180003c5b  mov     dword ptr [rsp+5D0h+var_5B0], eax
0x180003c5f  jmp     loc_180003F65
0x180003c64  lea     rax, [rbp+4D0h+var_260]
0x180003c6b  mov     rdx, rsi
0x180003c6e  inc     rdx
0x180003c71  cmp     [rax+rdx*2], r13w
0x180003c76  jnz     short loc_180003C6E
0x180003c78  add     rdx, 1
0x180003c7c  jz      loc_180003F30
0x180003c82  cmp     rdx, 7FFFFFFFh
0x180003c89  jbe     short loc_180003C95
0x180003c8b  mov     ebx, 80070057h
0x180003c90  jmp     loc_180003F3A
0x180003c95  mov     r14d, 7FFFFFFEh
0x180003c9b  lea     rcx, [rbp+4D0h+var_260]
0x180003ca2  mov     eax, r14d
0x180003ca5  test    rax, rax
0x180003ca8  jz      short loc_180003CC9
0x180003caa  movzx   r9d, word ptr [rcx]
0x180003cae  test    r9w, r9w
0x180003cb2  jz      short loc_180003CC9
0x180003cb4  mov     [r8], r9w
0x180003cb8  add     rcx, 2
0x180003cbc  add     r8, 2
0x180003cc0  dec     rax
0x180003cc3  sub     rdx, 1
0x180003cc7  jnz     short loc_180003CA5
0x180003cc9  mov     rax, rdx
0x180003ccc  lea     rcx, [r8-2]
0x180003cd0  neg     rax
0x180003cd3  sbb     ebx, ebx
0x180003cd5  not     ebx
0x180003cd7  and     ebx, 8007007Ah
0x180003cdd  test    rdx, rdx
0x180003ce0  cmovnz  rcx, r8
0x180003ce4  mov     [rcx], r13w
0x180003ce8  jz      loc_180003F3E
0x180003cee  lea     rax, [rbp+4D0h+var_470]
0x180003cf2  mov     rbx, rsi
0x180003cf5  inc     rbx
0x180003cf8  cmp     [rax+rbx*2], r13w
0x180003cfd  jnz     short loc_180003CF5
0x180003cff  lea     rbx, ds:2[rbx*2]
0x180003d07  call    cs:__imp_GetProcessHeap
0x180003d0d  mov     r8, rbx; dwBytes
0x180003d10  xor     edx, edx; dwFlags
0x180003d12  mov     rcx, rax; hHeap
0x180003d15  call    cs:__imp_HeapAlloc
0x180003d1b  mov     qword ptr [rsp+5D0h+var_580+8], rax
0x180003d20  mov     r8, rax
0x180003d23  test    rax, rax
0x180003d26  jnz     short loc_180003D3E
0x180003d28  mov     eax, 8007000Eh
0x180003d2d  mov     r9d, 1BCh
0x180003d33  mov     ebx, eax
0x180003d35  mov     dword ptr [rsp+5D0h+var_5B0], eax
0x180003d39  jmp     loc_180003F65
0x180003d3e  lea     rax, [rbp+4D0h+var_470]
0x180003d42  inc     rsi
0x180003d45  cmp     [rax+rsi*2], r13w
0x180003d4a  jnz     short loc_180003D42
0x180003d4c  lea     rdx, [rsi+1]
0x180003d50  test    rdx, rdx
0x180003d53  jz      short loc_180003DBE
0x180003d55  cmp     rdx, 7FFFFFFFh
0x180003d5c  jbe     short loc_180003D67
0x180003d5e  mov     ebx, 80070057h
0x180003d63  mov     ecx, ebx
0x180003d65  jmp     short loc_180003DCA
0x180003d67  lea     rax, [rbp+4D0h+var_470]
0x180003d6b  test    r14, r14
0x180003d6e  jz      short loc_180003D8D
0x180003d70  movzx   ecx, word ptr [rax]
0x180003d73  test    cx, cx
0x180003d76  jz      short loc_180003D8D
0x180003d78  mov     [r8], cx
0x180003d7c  add     rax, 2
0x180003d80  add     r8, 2
0x180003d84  dec     r14
0x180003d87  sub     rdx, 1
0x180003d8b  jnz     short loc_180003D6B
0x180003d8d  test    rdx, rdx
0x180003d90  lea     rcx, [r8-2]
0x180003d94  cmovnz  rcx, r8
0x180003d98  neg     rdx
0x180003d9b  mov     [rcx], r13w
0x180003d9f  sbb     ecx, ecx
0x180003da1  not     ecx
0x180003da3  and     ecx, 8007007Ah
0x180003da9  mov     ebx, ecx
0x180003dab  test    ecx, ecx
0x180003dad  jns     short loc_180003DD0
0x180003daf  mov     dword ptr [rsp+5D0h+var_5B0], ecx
0x180003db3  mov     r9d, 1BEh
0x180003db9  jmp     loc_180003F65
0x180003dbe  mov     ebx, 80070057h
0x180003dc3  mov     ecx, ebx
0x180003dc5  test    rdx, rdx
0x180003dc8  jz      short loc_180003DA9
0x180003dca  mov     [r8], r13w
0x180003dce  jmp     short loc_180003DAF
0x180003dd0  lea     rdx, [rbp+4D0h+var_510]
0x180003dd4  lea     rcx, [rbp+4D0h+var_530]
0x180003dd8  call    ?ProcessOccurrence@Throttler@@QEAA?AW4ThrottleResult@1@PEBG@Z; Throttler::ProcessOccurrence(ushort const *)
0x180003ddd  test    eax, eax
0x180003ddf  jz      short loc_180003E09
0x180003de1  sub     eax, 1
0x180003de4  jz      short loc_180003DFF
0x180003de6  sub     eax, 1
0x180003de9  jz      short loc_180003DF5
0x180003deb  mov     edi, 8
0x180003df0  jmp     loc_180003F7A
0x180003df5  mov     edi, 0Bh
0x180003dfa  jmp     loc_180003F7A
0x180003dff  mov     edi, 0Ch
0x180003e04  jmp     loc_180003F7A
0x180003e09  lea     rcx, [rsp+5D0h+var_58C]
0x180003e0e  mov     [rsp+5D0h+var_58C], 2
0x180003e16  call    GetGroupPolicySetting
0x180003e1b  mov     ebx, eax
0x180003e1d  test    eax, eax
0x180003e1f  jns     short loc_180003E30
0x180003e21  mov     dword ptr [rsp+5D0h+var_5B0], eax
0x180003e25  mov     r9d, 1E0h
0x180003e2b  jmp     loc_180003F65
0x180003e30  cmp     [rsp+5D0h+var_58C], 2
0x180003e35  jz      short loc_180003E45
0x180003e37  mov     edi, 14h
0x180003e3c  mov     dword ptr [rsp+5D0h+var_568+4], edi
0x180003e40  jmp     loc_180003F7A
0x180003e45  call    cs:__imp_GetTickCount64
0x180003e4b  mov     rcx, [rsp+5D0h+var_558]; unsigned __int16 *
0x180003e50  lea     r9, [rsp+5D0h+pnButton]; pnButton
0x180003e55  lea     r8, [rbp+4D0h+var_470]; unsigned __int16 *
0x180003e59  mov     [rsp+5D0h+pnButton], 7
0x180003e61  lea     rdx, [rbp+4D0h+var_260]; unsigned __int16 *
0x180003e68  mov     rsi, rax
0x180003e6b  call    ShowReinstallUI
0x180003e70  mov     ebx, eax
0x180003e72  test    eax, eax
0x180003e74  jns     short loc_180003E85
0x180003e76  mov     dword ptr [rsp+5D0h+var_5B0], eax
0x180003e7a  mov     r9d, 1F0h
0x180003e80  jmp     loc_180003F65
0x180003e85  call    cs:__imp_GetTickCount64
0x180003e8b  cmp     [rsp+5D0h+pnButton], 6
0x180003e90  mov     ecx, r13d
0x180003e93  mov     r8, rax
0x180003e96  mov     rax, 624DD2F1A9FBE77h
0x180003ea0  setnz   cl
0x180003ea3  sub     r8, rsi
0x180003ea6  mul     r8
0x180003ea9  inc     ecx
0x180003eab  sub     r8, rdx
0x180003eae  mov     dword ptr [rsp+5D0h+var_568], ecx
0x180003eb2  shr     r8, 1
0x180003eb5  add     r8, rdx
0x180003eb8  shr     r8, 9
0x180003ebc  cmp     [rsp+5D0h+pnButton], 6
0x180003ec1  mov     [rsp+5D0h+var_570], r8
0x180003ec6  jnz     short loc_180003F26
0x180003ec8  lea     rdx, aMsireinstallpr; "MsiReinstallProductW"
0x180003ecf  mov     rcx, r15; hModule
0x180003ed2  call    cs:__imp_GetProcAddress
0x180003ed8  test    rax, rax
0x180003edb  jnz     short loc_180003EEA
0x180003edd  mov     ebx, 80004005h
0x180003ee2  mov     r9d, 200h
0x180003ee8  jmp     short loc_180003F61
0x180003eea  mov     edx, 40h ; '@'
0x180003eef  lea     rcx, [rbp+4D0h+var_510]
0x180003ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ef8  test    eax, eax
0x180003efa  jg      short loc_180003F00
0x180003efc  mov     ebx, eax
0x180003efe  jmp     short loc_180003F09
0x180003f00  movzx   ebx, ax
0x180003f03  or      ebx, 80070000h
0x180003f09  test    ebx, ebx
0x180003f0b  jns     short loc_180003F1C
0x180003f0d  mov     edi, 11h
0x180003f12  mov     [rsp+5D0h+var_560], eax
0x180003f16  mov     dword ptr [rsp+5D0h+var_568+4], edi
0x180003f1a  jmp     short loc_180003F7A
0x180003f1c  mov     dword ptr [rsp+5D0h+var_568+4], 10h
0x180003f24  jmp     short loc_180003F7A
0x180003f26  mov     edi, 12h
0x180003f2b  jmp     loc_180003E3C
0x180003f30  mov     ebx, 80070057h
0x180003f35  test    rdx, rdx
0x180003f38  jz      short loc_180003F3E
0x180003f3a  mov     [r8], r13w
0x180003f3e  mov     r9d, 1BAh
0x180003f44  jmp     short loc_180003F61
0x180003f46  call    cs:__imp_GetLastError
0x180003f4c  mov     ebx, eax
0x180003f4e  test    eax, eax
0x180003f50  jle     short loc_180003F5B
0x180003f52  movzx   ebx, ax
0x180003f55  or      ebx, 80070000h
0x180003f5b  mov     r9d, 1A1h
  ... truncated ...
```
