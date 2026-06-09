# SmartlockerVerifyProcess

- ea: `0x14002f560`
- end: `0x14002fc42`
- name: `SmartlockerVerifyProcess`
- size: `1762`
- prototype: `__int64 __fastcall(int, int, int, int, char, int, __int64, int, PFILE_OBJECT FileObject, HANDLE FileHandle, char, char, char)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140030ff0`
- `0x140034550`

## callees

- `0x1400202ec`
- `0x140020344`
- `0x1400203f8`
- `0x140020518`
- `0x140022be0`
- `0x140022d58`
- `0x140023110`
- `0x14002f560`
- `0x14002fc50`
- `0x14002fe20`
- `0x140030620`
- `0x140030ab0`
- `0x140030c80`
- `0x1400315b0`
- `0x140032fc0`
- `0x140035c50`
- `0x140035e70`
- `0x140036020`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002f62e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f6ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f7f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fbb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fbd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fbee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fc08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fc1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f62e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f6ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f7f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fbb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fbd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fbee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fc08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fc1f`
- `ntoskrnl!ExAllocatePool2` at `0x14002f64f`
- `ntoskrnl!ExAllocatePool2` at `0x14002f64f`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x14002f684`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x14002f684`
- `ntoskrnl!ZwClose` at `0x14002f86c`
- `ntoskrnl!ZwClose` at `0x14002f86c`
- `ksecdd!BCryptGenRandom` at `0x14002f748`
- `ksecdd!BCryptGenRandom` at `0x14002f748`

## pseudocode

```c
__int64 __fastcall SmartlockerVerifyProcess(
        void *a1,
        void *a2,
        __int64 a3,
        const UNICODE_STRING *a4,
        char a5,
        unsigned int a6,
        __int64 a7,
        int a8,
        PFILE_OBJECT FileObject,
        HANDLE FileHandle,
        char a11,
        char a12,
        char a13)
{
  char v13; // r15
  _BYTE *v14; // r12
  __int64 Pool2; // rdi
  unsigned int v17; // r13d
  int v18; // esi
  __int64 v19; // r14
  void *v20; // r12
  unsigned int v21; // ebx
  int v22; // eax
  int v23; // r15d
  __int64 v24; // rax
  _DWORD *v25; // rcx
  unsigned int v26; // ebx
  unsigned int v27; // eax
  __int64 v28; // rcx
  unsigned int v29; // ebx
  __int64 v30; // rbx
  __int64 v31; // r14
  int v32; // ebx
  __int64 v33; // rsi
  char valid; // al
  unsigned int v35; // r12d
  int v36; // eax
  int v37; // eax
  char v38; // al
  int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // rcx
  int v42; // eax
  char v43; // dl
  __int64 v45; // [rsp+30h] [rbp-A1h]
  __int64 v46; // [rsp+38h] [rbp-99h]
  __int64 v47; // [rsp+58h] [rbp-79h]
  char v48; // [rsp+70h] [rbp-61h]
  unsigned int v49; // [rsp+74h] [rbp-5Dh]
  __int64 v50; // [rsp+78h] [rbp-59h] BYREF
  __int64 v51; // [rsp+80h] [rbp-51h] BYREF
  unsigned int v52; // [rsp+88h] [rbp-49h] BYREF
  unsigned int v53; // [rsp+8Ch] [rbp-45h]
  HANDLE Handle; // [rsp+90h] [rbp-41h] BYREF
  __int64 v55; // [rsp+98h] [rbp-39h] BYREF
  __int64 v56; // [rsp+A0h] [rbp-31h]
  PVOID P; // [rsp+A8h] [rbp-29h]
  __int64 v58; // [rsp+B0h] [rbp-21h]
  PVOID v59; // [rsp+B8h] [rbp-19h]
  PVOID v60; // [rsp+C0h] [rbp-11h] BYREF
  PVOID v61[9]; // [rsp+C8h] [rbp-9h] BYREF

  v13 = 0;
  v14 = (_BYTE *)a3;
  Pool2 = 0;
  v51 = 0;
  v17 = 1;
  v50 = 0;
  v59 = 0;
  v60 = 0;
  v55 = 0;
  v61[0] = 0;
  v56 = 0;
  v48 = 0;
  if ( *(int *)(a3 + 176) < 0
    || !*(_DWORD *)(*(_QWORD *)(a3 + 184) + 12LL)
    || (v18 = SmartlockerManagedInstallerCheck(a1, a2, a3, a4, a5, (unsigned int *)&v50, &v51), v18 < 0) )
  {
    v18 = 0;
    v49 = 5;
    v58 = 0;
    v20 = a1;
    v53 = 0;
    P = 0;
    while ( 2 )
    {
      if ( Pool2 )
        ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
      v21 = 436;
      v52 = 0;
      while ( 1 )
      {
        Pool2 = ExAllocatePool2(258, v21, 1098149235, a4);
        if ( !Pool2 )
          goto LABEL_37;
        v22 = ZwQuerySecurityAttributesToken(v20, L"24", 1, Pool2, v21, &v52);
        if ( v22 != -1073741789 )
          break;
        if ( v21 >= v52 )
          goto LABEL_36;
        v21 = v52;
        ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
      }
      if ( v22 < 0 )
      {
LABEL_36:
        ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
        Pool2 = 0;
LABEL_37:
        v51 = 0;
        LODWORD(v50) = 0;
      }
      else
      {
        v23 = 326;
        v19 = 0;
        if ( *(_DWORD *)(Pool2 + 4)
          && (v24 = *(_QWORD *)(Pool2 + 8), *(_WORD *)(v24 + 16) == 16)
          && (v25 = *(_DWORD **)(v24 + 32), v26 = v25[2], v26 >= 0x40) )
        {
          v19 = *(_QWORD *)v25;
          v23 = v25[2];
          v27 = *(_DWORD *)(*(_QWORD *)v25 + 8LL);
          if ( v27 > 1 )
          {
            v18 = -1073741823;
            if ( v27 == 4 )
              v18 = 0;
          }
          if ( !a12 && !*(_DWORD *)(v19 + 4) )
          {
            v28 = *(_QWORD *)(v19 + 32) - *(_QWORD *)(v19 + 16);
            if ( !v28 )
              v28 = *(_QWORD *)(v19 + 40) - *(_QWORD *)(v19 + 24);
            if ( !v28 )
            {
              v48 = 1;
              BCryptGenRandom(0, (PUCHAR)(v19 + 32), 0x10u, 2u);
              SmartlockerTagProcessToken(v20, v26, v19);
            }
          }
        }
        else
        {
          v18 = -1073741823;
        }
        v29 = 0;
        v51 = v19;
        if ( v19 )
          v29 = v23;
        v13 = v48;
        LODWORD(v50) = v29;
        if ( v18 >= 0 )
          goto LABEL_59;
        v18 = 0;
        if ( v19 )
        {
          v53 = v29;
          v30 = (__int64)a2;
          v58 = v19;
          break;
        }
      }
      v30 = (__int64)a2;
      if ( v20 != a2 )
      {
        v20 = a2;
        continue;
      }
      break;
    }
    v31 = (__int64)a1;
    if ( a13 )
    {
      v18 = SmartlockerSmartscreenProcessTokenCheck((__int64)a1, v30, (unsigned int *)&v50, &v51);
      if ( v18 >= 0 )
      {
        v19 = v51;
        v13 = 1;
        P = (PVOID)v51;
        v49 = 1;
LABEL_63:
        v14 = (_BYTE *)a3;
        goto LABEL_64;
      }
    }
    if ( a12 )
    {
      v35 = HIDWORD(v50);
LABEL_54:
      v36 = SmartlockerCheckEA(
              v31,
              v30,
              (_DWORD)FileObject,
              (_DWORD)FileHandle,
              (__int64)&v50,
              (__int64)&v51,
              (__int64)v61);
      v19 = v51;
      v18 = v36;
      if ( v36 >= 0 || v36 == -1073741823 && v51 )
      {
        v49 = 3;
        goto LABEL_63;
      }
      if ( !v58 )
      {
        if ( v55 )
        {
          v19 = v55;
          v49 = 7;
          v29 = v35;
          v37 = SmartlockerTagProcessToken(a2, v35, v55);
          v14 = (_BYTE *)a3;
          v18 = v37;
          goto LABEL_65;
        }
        goto LABEL_63;
      }
      v29 = v53;
      v19 = v58;
LABEL_59:
      v14 = (_BYTE *)a3;
      v49 = 2;
      goto LABEL_65;
    }
    Handle = 0;
    if ( (int)AiOpenTokenByProcessId((void *)a6, &Handle) >= 0 )
    {
      v32 = SmartlockerOriginClaimProcessTokenCheck((__int64)Handle, 0, 0, (int *)&v50 + 1, &v55, (__int64 *)&v60);
      ZwClose(Handle);
      if ( v32 >= 0 )
      {
        v33 = v55;
        valid = IsValidManagedInstallerOrigin(v55, 7);
        v35 = HIDWORD(v50);
        if ( valid )
        {
          v29 = HIDWORD(v50);
          LODWORD(v50) = HIDWORD(v50);
          v51 = v33;
          v19 = v33;
          v18 = SmartlockerTagProcessToken(a2, HIDWORD(v50), v33);
          if ( v18 >= 0 )
          {
            v14 = (_BYTE *)a3;
            v49 = 7;
            goto LABEL_65;
          }
          v30 = (__int64)a2;
          v31 = (__int64)a1;
        }
        else
        {
          v30 = (__int64)a2;
        }
LABEL_50:
        if ( a7 )
        {
          v18 = SmartlockerCheckUninstallStringEA(v31, v30, a7, (__int64)FileObject, (unsigned int *)&v50, &v51);
          if ( v18 >= 0 )
          {
            v19 = v51;
            v59 = (PVOID)v51;
            v49 = 8;
            SmartlockerCheckUSN(FileObject, FileHandle);
            v29 = v50;
            v14 = (_BYTE *)a3;
            goto LABEL_67;
          }
        }
        goto LABEL_54;
      }
      v30 = (__int64)a2;
    }
    v35 = HIDWORD(v50);
    goto LABEL_50;
  }
  v19 = v51;
  P = (PVOID)v51;
  v49 = 0;
LABEL_64:
  v29 = v50;
LABEL_65:
  SmartlockerCheckUSN(FileObject, FileHandle);
  v38 = a12;
  if ( a7 )
  {
    if ( !a12 )
    {
LABEL_67:
      v39 = SrppPluginAccessCheck(a1);
      v40 = v49;
      if ( v39 )
      {
        v17 = 0;
      }
      else if ( v19 && (unsigned __int8)IsValidManagedInstallerOrigin(v19, v49) )
      {
        AiAddProcToOriginList(a7, v19, v29);
        v40 = v49;
      }
      else if ( a11 )
      {
        AiAddProcToTrackedList(a7, v40);
        v40 = v49;
      }
      if ( v19 )
      {
        if ( !(unsigned __int8)IsValidManagedInstallerOrigin(v19, v40) )
          goto LABEL_82;
        v41 = *(_QWORD *)(v19 + 16) - *(_QWORD *)(v19 + 32);
        if ( !v41 )
          v41 = *(_QWORD *)(v19 + 24) - *(_QWORD *)(v19 + 40);
        if ( v41 )
        {
          AiAddSessionToOriginList(a7, v19, v29);
        }
        else
        {
LABEL_82:
          if ( (_DWORD)v40 == 3 )
          {
            v42 = *(_DWORD *)(v19 + 8);
            if ( !v42 || v42 == 3 )
              AiAddProcToTrackedSessionList(a7, v17, v19);
          }
        }
      }
      SmartlockerAddChildProcToTrackedListIfParentPresent(a7, v40);
      if ( v13 && (unsigned int)SrppPluginAccessCheck(a1) )
        AiSetSmartlockerEAs(FileHandle);
      v38 = a12;
      goto LABEL_88;
    }
LABEL_94:
    v43 = v14[285] == 0;
    goto LABEL_89;
  }
  if ( a12 )
    goto LABEL_94;
LABEL_88:
  v43 = v14[261] == 0;
LABEL_89:
  if ( v19 && v18 == -1073741275 )
    v18 = -1073741823;
  SmartlockerTelemetrizeOriginInfo(
    (__int64)a1,
    (__int64)a4,
    FileHandle,
    v18,
    v49,
    v56,
    v45,
    v46,
    v43,
    v14[333] == 0,
    a8,
    v47,
    v19,
    v38);
  if ( P )
    ExFreePoolWithTag(P, 0x41746D73u);
  if ( v59 )
    ExFreePoolWithTag(v59, 0x41746D73u);
  if ( Pool2 )
    ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
  if ( v60 )
    ExFreePoolWithTag(v60, 0x41746D73u);
  if ( v61[0] )
    ExFreePoolWithTag(v61[0], 0);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14002f560  mov     [rsp-8+arg_18], r9
0x14002f565  mov     [rsp-8+arg_10], r8
0x14002f56a  mov     [rsp-8+arg_8], rdx
0x14002f56f  mov     [rsp-8+arg_0], rcx
0x14002f574  push    rbp
0x14002f575  push    rbx
0x14002f576  push    rsi
0x14002f577  push    rdi
0x14002f578  push    r12
0x14002f57a  push    r13
0x14002f57c  push    r14
0x14002f57e  push    r15
0x14002f580  lea     rbp, [rsp-7]
0x14002f585  sub     rsp, 0D8h
0x14002f58c  xor     eax, eax
0x14002f58e  xor     r15b, r15b
0x14002f591  mov     r12, r8
0x14002f594  mov     r14, rcx
0x14002f597  mov     edi, eax
0x14002f599  mov     [rbp+3Fh+var_90], rax
0x14002f59d  mov     r13d, 1
0x14002f5a3  mov     dword ptr [rbp+3Fh+var_98], eax
0x14002f5a6  mov     [rbp+3Fh+var_58], rax
0x14002f5aa  mov     [rbp+3Fh+var_50], rax
0x14002f5ae  mov     [rbp+3Fh+var_78], rax
0x14002f5b2  mov     dword ptr [rbp+3Fh+var_98+4], eax
0x14002f5b5  mov     [rbp+3Fh+var_48], rax
0x14002f5b9  mov     [rbp+3Fh+var_70], rax
0x14002f5bd  mov     [rbp+3Fh+var_A0], r15b
0x14002f5c1  cmp     [r8+0B0h], eax
0x14002f5c8  jl      short loc_14002F60A
0x14002f5ca  mov     rax, [r8+0B8h]
0x14002f5d1  cmp     [rax+0Ch], edi
0x14002f5d4  jz      short loc_14002F60A
0x14002f5d6  lea     rax, [rbp+3Fh+var_90]
0x14002f5da  mov     [rsp+110h+var_E0], rax; __int64
0x14002f5df  lea     rax, [rbp+3Fh+var_98]
0x14002f5e3  mov     [rsp+110h+var_E8], rax; __int64
0x14002f5e8  mov     eax, dword ptr [rbp+3Fh+arg_20]
0x14002f5eb  mov     dword ptr [rsp+110h+var_F0], eax; char
0x14002f5ef  call    SmartlockerManagedInstallerCheck
0x14002f5f4  mov     esi, eax
0x14002f5f6  test    eax, eax
0x14002f5f8  js      short loc_14002F60A
0x14002f5fa  mov     r14, [rbp+3Fh+var_90]
0x14002f5fe  mov     [rbp+3Fh+P], r14
0x14002f602  mov     [rbp+3Fh+var_9C], edi
0x14002f605  jmp     loc_14002F9E6
0x14002f60a  xor     esi, esi
0x14002f60c  mov     [rbp+3Fh+var_9C], 5
0x14002f613  mov     [rbp+3Fh+var_60], rsi
0x14002f617  mov     r12, r14
0x14002f61a  mov     [rbp+3Fh+var_84], esi
0x14002f61d  mov     [rbp+3Fh+P], rsi
0x14002f621  test    rdi, rdi
0x14002f624  jz      short loc_14002F63A
0x14002f626  mov     edx, 41746D73h; Tag
0x14002f62b  mov     rcx, rdi; P
0x14002f62e  call    cs:__imp_ExFreePoolWithTag
0x14002f635  nop     dword ptr [rax+rax+00h]
0x14002f63a  mov     ebx, 1B4h
0x14002f63f  mov     [rbp+3Fh+var_88], esi
0x14002f642  mov     edx, ebx
0x14002f644  mov     ecx, 102h
0x14002f649  mov     r8d, 41746D73h
0x14002f64f  call    cs:__imp_ExAllocatePool2
0x14002f656  nop     dword ptr [rax+rax+00h]
0x14002f65b  mov     rdi, rax
0x14002f65e  test    rax, rax
0x14002f661  jz      loc_14002F803
0x14002f667  lea     rax, [rbp+3Fh+var_88]
0x14002f66b  mov     r9, rdi
0x14002f66e  mov     [rsp+110h+var_E8], rax
0x14002f673  lea     rdx, a24; "24"
0x14002f67a  mov     r8d, r13d
0x14002f67d  mov     dword ptr [rsp+110h+var_F0], ebx
0x14002f681  mov     rcx, r12
0x14002f684  call    cs:__imp_ZwQuerySecurityAttributesToken
0x14002f68b  nop     dword ptr [rax+rax+00h]
0x14002f690  cmp     eax, 0C0000023h
0x14002f695  jnz     short loc_14002F6BA
0x14002f697  mov     eax, [rbp+3Fh+var_88]
0x14002f69a  cmp     ebx, eax
0x14002f69c  jnb     loc_14002F7EC
0x14002f6a2  mov     edx, 41746D73h; Tag
0x14002f6a7  mov     rcx, rdi; P
0x14002f6aa  mov     ebx, eax
0x14002f6ac  call    cs:__imp_ExFreePoolWithTag
0x14002f6b3  nop     dword ptr [rax+rax+00h]
0x14002f6b8  jmp     short loc_14002F642
0x14002f6ba  test    eax, eax
0x14002f6bc  js      loc_14002F7EC
0x14002f6c2  cmp     dword ptr [rdi+4], 0
0x14002f6c6  mov     r15d, 146h
0x14002f6cc  mov     r14, rsi
0x14002f6cf  jbe     loc_14002F768
0x14002f6d5  mov     rax, [rdi+8]
0x14002f6d9  cmp     word ptr [rax+10h], 10h
0x14002f6de  jnz     loc_14002F768
0x14002f6e4  mov     rcx, [rax+20h]
0x14002f6e8  mov     ebx, [rcx+8]
0x14002f6eb  cmp     ebx, 40h ; '@'
0x14002f6ee  jb      short loc_14002F768
0x14002f6f0  mov     r14, [rcx]
0x14002f6f3  mov     r15d, ebx
0x14002f6f6  mov     ecx, 0C0000001h
0x14002f6fb  mov     eax, [r14+8]
0x14002f6ff  cmp     eax, r13d
0x14002f702  jbe     short loc_14002F70D
0x14002f704  mov     esi, ecx
0x14002f706  cmp     eax, 4
0x14002f709  jnz     short loc_14002F70D
0x14002f70b  xor     esi, esi
0x14002f70d  cmp     [rbp+3Fh+arg_58], 0
0x14002f714  jnz     short loc_14002F76F
0x14002f716  cmp     dword ptr [r14+4], 0
0x14002f71b  jnz     short loc_14002F76F
0x14002f71d  mov     rcx, [r14+20h]
0x14002f721  lea     rdx, [r14+20h]; pbBuffer
0x14002f725  sub     rcx, [r14+10h]
0x14002f729  jnz     short loc_14002F733
0x14002f72b  mov     rcx, [rdx+8]
0x14002f72f  sub     rcx, [r14+18h]; hAlgorithm
0x14002f733  test    rcx, rcx
0x14002f736  jnz     short loc_14002F761
0x14002f738  mov     r9d, 2; dwFlags
0x14002f73e  mov     [rbp+3Fh+var_A0], r13b
0x14002f742  mov     r8d, 10h; cbBuffer
0x14002f748  call    cs:__imp_BCryptGenRandom
0x14002f74f  nop     dword ptr [rax+rax+00h]
0x14002f754  mov     r8, r14
0x14002f757  mov     edx, ebx
0x14002f759  mov     rcx, r12
0x14002f75c  call    SmartlockerTagProcessToken
0x14002f761  mov     ecx, 0C0000001h
0x14002f766  jmp     short loc_14002F76F
0x14002f768  mov     ecx, 0C0000001h
0x14002f76d  mov     esi, ecx
0x14002f76f  xor     ebx, ebx
0x14002f771  mov     [rbp+3Fh+var_90], r14
0x14002f775  test    r14, r14
0x14002f778  mov     rax, rdi
0x14002f77b  cmovnz  ebx, r15d
0x14002f77f  movzx   r15d, [rbp+3Fh+var_A0]
0x14002f784  mov     dword ptr [rbp+3Fh+var_98], ebx
0x14002f787  test    esi, esi
0x14002f789  jns     loc_14002F9A4
0x14002f78f  mov     [rbp+3Fh+var_A0], r15b
0x14002f793  cmp     esi, ecx
0x14002f795  jnz     short loc_14002F7E4
0x14002f797  xor     esi, esi
0x14002f799  test    r14, r14
0x14002f79c  jz      short loc_14002F80A
0x14002f79e  mov     [rbp+3Fh+var_84], ebx
0x14002f7a1  mov     rbx, [rbp+3Fh+arg_8]
0x14002f7a5  mov     [rbp+3Fh+var_60], r14
0x14002f7a9  cmp     [rbp+3Fh+arg_60], 0
0x14002f7b0  mov     r14, [rbp+3Fh+arg_0]
0x14002f7b4  jz      short loc_14002F81D
0x14002f7b6  lea     r9, [rbp+3Fh+var_90]
0x14002f7ba  mov     rdx, rbx
0x14002f7bd  lea     r8, [rbp+3Fh+var_98]
0x14002f7c1  mov     rcx, r14
0x14002f7c4  call    SmartlockerSmartscreenProcessTokenCheck
0x14002f7c9  mov     esi, eax
0x14002f7cb  test    eax, eax
0x14002f7cd  js      short loc_14002F81B
0x14002f7cf  mov     r14, [rbp+3Fh+var_90]
0x14002f7d3  movzx   r15d, r13b
0x14002f7d7  mov     [rbp+3Fh+P], r14
0x14002f7db  mov     [rbp+3Fh+var_9C], r13d
0x14002f7df  jmp     loc_14002F9E2
0x14002f7e4  mov     [rbp+3Fh+var_A0], r15b
0x14002f7e8  xor     esi, esi
0x14002f7ea  jmp     short loc_14002F80A
0x14002f7ec  mov     edx, 41746D73h; Tag
0x14002f7f1  mov     rcx, rdi; P
0x14002f7f4  call    cs:__imp_ExFreePoolWithTag
0x14002f7fb  nop     dword ptr [rax+rax+00h]
0x14002f800  mov     rdi, rsi
0x14002f803  mov     [rbp+3Fh+var_90], rsi
0x14002f807  mov     dword ptr [rbp+3Fh+var_98], esi
0x14002f80a  mov     rbx, [rbp+3Fh+arg_8]
0x14002f80e  cmp     r12, rbx
0x14002f811  jz      short loc_14002F7A9
0x14002f813  mov     r12, rbx
0x14002f816  jmp     loc_14002F621
0x14002f81b  xor     esi, esi
0x14002f81d  cmp     [rbp+3Fh+arg_58], 0
0x14002f824  jnz     loc_14002F947
0x14002f82a  mov     ecx, [rbp+3Fh+arg_28]
0x14002f82d  lea     rdx, [rbp+3Fh+Handle]
0x14002f831  mov     [rbp+3Fh+Handle], rsi
0x14002f835  call    AiOpenTokenByProcessId
0x14002f83a  test    eax, eax
0x14002f83c  js      loc_14002F8DB
0x14002f842  mov     rcx, [rbp+3Fh+Handle]
0x14002f846  lea     rax, [rbp+3Fh+var_50]
0x14002f84a  mov     [rsp+110h+var_E8], rax
0x14002f84f  lea     r9, [rbp+3Fh+var_98+4]
0x14002f853  lea     rax, [rbp+3Fh+var_78]
0x14002f857  xor     r8d, r8d
0x14002f85a  xor     edx, edx
0x14002f85c  mov     qword ptr [rsp+110h+var_F0], rax
0x14002f861  call    SmartlockerOriginClaimProcessTokenCheck
0x14002f866  mov     rcx, [rbp+3Fh+Handle]; Handle
0x14002f86a  mov     ebx, eax
0x14002f86c  call    cs:__imp_ZwClose
0x14002f873  nop     dword ptr [rax+rax+00h]
0x14002f878  test    ebx, ebx
0x14002f87a  js      short loc_14002F8D7
0x14002f87c  mov     rsi, [rbp+3Fh+var_78]
0x14002f880  mov     edx, 7
0x14002f885  mov     rcx, rsi
0x14002f888  call    IsValidManagedInstallerOrigin
0x14002f88d  mov     r12d, dword ptr [rbp+3Fh+var_98+4]
0x14002f891  test    al, al
0x14002f893  jz      short loc_14002F8D1
0x14002f895  mov     rcx, [rbp+3Fh+arg_8]
0x14002f899  mov     ebx, r12d
0x14002f89c  mov     r8, rsi
0x14002f89f  mov     dword ptr [rbp+3Fh+var_98], ebx
0x14002f8a2  mov     edx, r12d
0x14002f8a5  mov     [rbp+3Fh+var_90], rsi
0x14002f8a9  mov     r14, rsi
0x14002f8ac  call    SmartlockerTagProcessToken
0x14002f8b1  mov     esi, eax
0x14002f8b3  test    eax, eax
0x14002f8b5  js      short loc_14002F8C7
0x14002f8b7  mov     r12, [rbp+3Fh+arg_10]
0x14002f8bb  mov     [rbp+3Fh+var_9C], 7
0x14002f8c2  jmp     loc_14002F9E9
0x14002f8c7  mov     rbx, [rbp+3Fh+arg_8]
0x14002f8cb  mov     r14, [rbp+3Fh+arg_0]
0x14002f8cf  jmp     short loc_14002F8DF
0x14002f8d1  mov     rbx, [rbp+3Fh+arg_8]
0x14002f8d5  jmp     short loc_14002F8DF
0x14002f8d7  mov     rbx, [rbp+3Fh+arg_8]
0x14002f8db  mov     r12d, dword ptr [rbp+3Fh+var_98+4]
0x14002f8df  mov     rax, [rbp+3Fh+arg_30]
0x14002f8e3  test    rax, rax
0x14002f8e6  jz      short loc_14002F94B
0x14002f8e8  mov     r9, [rbp+3Fh+FileObject]
0x14002f8ef  lea     rcx, [rbp+3Fh+var_90]
0x14002f8f3  mov     [rsp+110h+var_E8], rcx
0x14002f8f8  mov     r8, rax
0x14002f8fb  lea     rcx, [rbp+3Fh+var_98]
0x14002f8ff  mov     rdx, rbx
0x14002f902  mov     qword ptr [rsp+110h+var_F0], rcx
0x14002f907  mov     rcx, r14
0x14002f90a  call    SmartlockerCheckUninstallStringEA
0x14002f90f  mov     esi, eax
0x14002f911  test    eax, eax
0x14002f913  js      short loc_14002F94B
0x14002f915  mov     r14, [rbp+3Fh+var_90]
0x14002f919  lea     r8, [rbp+3Fh+var_70]
0x14002f91d  mov     rdx, [rbp+3Fh+FileHandle]; FileHandle
0x14002f924  mov     rcx, [rbp+3Fh+FileObject]; FileObject
0x14002f92b  mov     [rbp+3Fh+var_58], r14
0x14002f92f  mov     [rbp+3Fh+var_9C], 8
0x14002f936  call    SmartlockerCheckUSN
0x14002f93b  mov     ebx, dword ptr [rbp+3Fh+var_98]
0x14002f93e  mov     r12, [rbp+3Fh+arg_10]
0x14002f942  jmp     loc_14002FA1A
0x14002f947  mov     r12d, dword ptr [rbp+3Fh+var_98+4]
0x14002f94b  mov     r9, [rbp+3Fh+FileHandle]
0x14002f952  lea     rax, [rbp+3Fh+var_48]
0x14002f956  mov     r8, [rbp+3Fh+FileObject]
0x14002f95d  mov     rdx, rbx
0x14002f960  mov     [rsp+110h+var_E0], rax
0x14002f965  mov     rcx, r14
0x14002f968  lea     rax, [rbp+3Fh+var_90]
0x14002f96c  mov     [rsp+110h+var_E8], rax
0x14002f971  lea     rax, [rbp+3Fh+var_98]
0x14002f975  mov     qword ptr [rsp+110h+var_F0], rax
0x14002f97a  call    SmartlockerCheckEA
0x14002f97f  mov     r14, [rbp+3Fh+var_90]
0x14002f983  mov     esi, eax
0x14002f985  test    eax, eax
0x14002f987  jns     short loc_14002F9DB
0x14002f989  cmp     eax, 0C0000001h
0x14002f98e  jnz     short loc_14002F995
0x14002f990  test    r14, r14
0x14002f993  jnz     short loc_14002F9DB
0x14002f995  mov     rax, [rbp+3Fh+var_60]
0x14002f999  test    rax, rax
0x14002f99c  jz      short loc_14002F9B1
0x14002f99e  mov     ebx, [rbp+3Fh+var_84]
0x14002f9a1  mov     r14, rax
0x14002f9a4  mov     r12, [rbp+3Fh+arg_10]
0x14002f9a8  mov     [rbp+3Fh+var_9C], 2
0x14002f9af  jmp     short loc_14002F9E9
0x14002f9b1  mov     r8, [rbp+3Fh+var_78]
0x14002f9b5  test    r8, r8
0x14002f9b8  jz      short loc_14002F9E2
0x14002f9ba  mov     rcx, [rbp+3Fh+arg_8]
0x14002f9be  mov     edx, r12d
0x14002f9c1  mov     r14, r8
0x14002f9c4  mov     [rbp+3Fh+var_9C], 7
0x14002f9cb  mov     ebx, r12d
  ... truncated ...
```
