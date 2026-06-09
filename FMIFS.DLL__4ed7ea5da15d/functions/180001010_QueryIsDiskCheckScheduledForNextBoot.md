# QueryIsDiskCheckScheduledForNextBoot

- ea: `0x180001010`
- end: `0x180001381`
- name: `QueryIsDiskCheckScheduledForNextBoot`
- size: `881`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180001010`
- `0x180001390`
- `0x1800015d0`
- `0x180009780`

## import_xrefs

- `msvcrt!free` at `0x18000115b`
- `msvcrt!free` at `0x18000115b`
- `msvcrt!realloc` at `0x1800010c6`
- `msvcrt!realloc` at `0x1800010c6`
- `ntdll!RtlNtStatusToDosError` at `0x180001345`
- `ntdll!RtlNtStatusToDosError` at `0x180001345`
- `ntdll!RtlAllocateHeap` at `0x18000124a`
- `ntdll!RtlAllocateHeap` at `0x18000124a`
- `ntdll!RtlFreeHeap` at `0x1800012a3`
- `ntdll!RtlFreeHeap` at `0x1800012a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800012e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000134d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001369`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800012e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000134d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001369`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800011e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800011e5`
- `ulib!?Stricmp@WSTRING@@QEBAJPEBV1@KKKK@Z` at `0x18000131a`
- `ulib!?Stricmp@WSTRING@@QEBAJPEBV1@KKKK@Z` at `0x18000131a`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x18000111a`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180001142`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x1800011c2`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x18000111a`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180001142`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x1800011c2`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180001057`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180001061`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180001057`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180001061`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180001165`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000116f`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180001165`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000116f`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x1800012f1`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x1800012fd`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x1800012f1`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x1800012fd`
- `IfsUtil!QueryPersistRegistryKeyValueWithFallback` at `0x1800010fb`
- `IfsUtil!QueryPersistRegistryKeyValueWithFallback` at `0x1800010fb`

## string_xrefs

- `0x1800010e3`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager`

## pseudocode

```c
__int64 __fastcall QueryIsDiskCheckScheduledForNextBoot(_BYTE *a1)
{
  void *v2; // rsi
  unsigned int v3; // ebx
  unsigned __int8 v4; // r14
  void *v5; // rax
  NTSTATUS v6; // eax
  const unsigned __int16 *v7; // rbx
  const unsigned __int16 *v9; // rdi
  unsigned __int16 *v10; // r13
  int v11; // ebx
  int v12; // r12d
  unsigned __int16 **Heap; // rax
  unsigned __int16 **v14; // r15
  unsigned __int8 v15; // bl
  unsigned int ChCount; // edi
  unsigned int v18; // eax
  DWORD v20; // eax
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE *v23; // [rsp+38h] [rbp-C8h]
  __int128 v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+58h] [rbp-A8h]
  const wchar_t *v27; // [rsp+60h] [rbp-A0h]
  __int128 *v28; // [rsp+68h] [rbp-98h]
  int v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  int v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 v35; // [rsp+A0h] [rbp-60h]
  int v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  int v38; // [rsp+B8h] [rbp-48h]
  _BYTE v39[48]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v40[48]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Filename[264]; // [rsp+120h] [rbp+20h] BYREF

  v23 = a1;
  v2 = 0;
  v24 = 0;
  DSTRING::DSTRING((DSTRING *)v39);
  DSTRING::DSTRING((DSTRING *)v40);
  v21 = 0;
  v27 = L"BootExecute";
  v3 = 0x2000;
  v25 = 0;
  v28 = &v24;
  v4 = 0;
  v26 = 48;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  while ( 1 )
  {
    v5 = realloc(v2, v3);
    v2 = v5;
    if ( !v5 )
    {
      SetLastError(8u);
      goto LABEL_9;
    }
    LOWORD(v24) = 0;
    WORD1(v24) = v3;
    *((_QWORD *)&v24 + 1) = v5;
    v6 = QueryPersistRegistryKeyValueWithFallback(
           L"Session Manager",
           L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control\\Session Manager",
           &v25);
    if ( v6 >= 0 )
      break;
    if ( v6 != -1073741789 )
    {
      v20 = RtlNtStatusToDosError(v6);
      SetLastError(v20);
      goto LABEL_8;
    }
    v3 *= 2;
  }
  if ( !WSTRING::Initialize((WSTRING *)v39, L"autocheck autochk", 0xFFFFFFFF) )
    goto LABEL_8;
  v7 = (const unsigned __int16 *)v2;
  while ( *v7 )
  {
    if ( !WSTRING::Initialize((WSTRING *)v40, v7, 0xFFFFFFFF) )
      goto LABEL_8;
    ChCount = WSTRING::QueryChCount((WSTRING *)v39);
    v18 = WSTRING::QueryChCount((WSTRING *)v39);
    if ( WSTRING::Stricmp((WSTRING *)v40, (const struct WSTRING *)v39, 0, v18, 0, ChCount) )
    {
      *a1 = 1;
      v4 = 1;
      goto LABEL_8;
    }
    while ( *v7++ )
      ;
  }
  v9 = (const unsigned __int16 *)v2;
  while ( 1 )
  {
    if ( !*v9 )
    {
      *v23 = 0;
      goto LABEL_21;
    }
    if ( !WSTRING::Initialize((WSTRING *)v40, v9, 0xFFFFFFFF) )
      goto LABEL_8;
    v22 = 0;
    v9 += 10;
    GetModuleFileNameW(0, Filename, 0x104u);
    v10 = Filename;
    if ( *v9 )
      v10 = (unsigned __int16 *)v9;
    Parse_Cmdline(v10, 0, 0, &v21, &v22, 0);
    v11 = v21;
    if ( (unsigned int)v21 < (unsigned __int64)~(__int64)v22 >> 3 )
    {
      v12 = v22 + 8 * v21;
      Heap = (unsigned __int16 **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      v14 = Heap;
      if ( !Heap )
      {
        SetLastError(8u);
        goto LABEL_18;
      }
      Parse_Cmdline(v10, Heap, (unsigned __int16 *)&Heap[v11], &v21, &v22, v12);
      v15 = SimulateAutochkMainInvocation(v21, v14);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
      if ( v15 )
        break;
    }
LABEL_18:
    while ( *v9++ )
      ;
  }
  *v23 = 1;
LABEL_21:
  v4 = 1;
LABEL_8:
  free(v2);
LABEL_9:
  DSTRING::~DSTRING((DSTRING *)v40);
  DSTRING::~DSTRING((DSTRING *)v39);
  return v4;
}

```

## disassembly

```asm
0x180001010  mov     [rsp-8+arg_18], rbx
0x180001015  push    rbp
0x180001016  push    rsi
0x180001017  push    r12
0x180001019  push    r14
0x18000101b  push    r15
0x18000101d  lea     rbp, [rsp-240h]
0x180001025  sub     rsp, 340h
0x18000102c  mov     rax, cs:__security_cookie
0x180001033  xor     rax, rsp
0x180001036  mov     [rbp+260h+var_30], rax
0x18000103d  mov     r15, rcx
0x180001040  mov     [rsp+360h+var_328], rcx
0x180001045  xorps   xmm0, xmm0
0x180001048  lea     rcx, [rbp+260h+var_2A0]
0x18000104c  xor     r12d, r12d
0x18000104f  mov     esi, r12d
0x180001052  movups  [rsp+360h+var_320], xmm0
0x180001057  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x18000105d  lea     rcx, [rbp+260h+var_270]
0x180001061  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180001067  lea     rax, aBootexecute; "BootExecute"
0x18000106e  mov     [rsp+360h+var_330], r12d
0x180001073  mov     [rsp+360h+var_300], rax
0x180001078  mov     ebx, 2000h
0x18000107d  lea     rax, [rsp+360h+var_320]
0x180001082  mov     [rsp+360h+var_310], r12
0x180001087  mov     [rsp+360h+var_2F8], rax
0x18000108c  xor     r14b, r14b
0x18000108f  mov     [rsp+360h+var_308], 30h ; '0'
0x180001097  mov     [rsp+360h+var_2F0], r12d
0x18000109c  mov     [rsp+360h+var_2E8], r12
0x1800010a1  mov     [rbp+260h+var_2E0], r12d
0x1800010a5  mov     [rbp+260h+var_2D8], r12
0x1800010a9  mov     [rbp+260h+var_2D0], r12d
0x1800010ad  mov     [rbp+260h+var_2C8], r12
0x1800010b1  mov     [rbp+260h+var_2C0], r12
0x1800010b5  mov     [rbp+260h+var_2B8], r12d
0x1800010b9  mov     [rbp+260h+var_2B0], r12
0x1800010bd  mov     [rbp+260h+var_2A8], r12d
0x1800010c1  mov     edx, ebx; Size
0x1800010c3  mov     rcx, rsi; Block
0x1800010c6  call    cs:__imp_realloc
0x1800010cc  mov     rsi, rax
0x1800010cf  test    rax, rax
0x1800010d2  jz      loc_1800012DD
0x1800010d8  lea     r8, [rsp+360h+var_310]
0x1800010dd  mov     word ptr [rsp+360h+var_320], r12w
0x1800010e3  lea     rdx, aRegistryMachin; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x1800010ea  mov     word ptr [rsp+360h+var_320+2], bx
0x1800010ef  lea     rcx, aSessionManager; "Session Manager"
0x1800010f6  mov     qword ptr [rsp+360h+var_320+8], rax
0x1800010fb  call    cs:__imp_QueryPersistRegistryKeyValueWithFallback
0x180001101  test    eax, eax
0x180001103  js      loc_180001335
0x180001109  mov     r8d, 0FFFFFFFFh
0x18000110f  lea     rdx, aAutocheckAutoc; "autocheck autochk"
0x180001116  lea     rcx, [rbp+260h+var_2A0]
0x18000111a  call    cs:__imp_?Initialize@WSTRING@@QEAAEPEBGK@Z; WSTRING::Initialize(ushort const *,ulong)
0x180001120  test    al, al
0x180001122  jz      short loc_180001158
0x180001124  mov     rbx, rsi
0x180001127  mov     [rsp+360h+arg_8], rdi
0x18000112f  cmp     [rbx], r12w
0x180001133  jz      short loc_1800011A0
0x180001135  mov     r8d, 0FFFFFFFFh
0x18000113b  lea     rcx, [rbp+260h+var_270]
0x18000113f  mov     rdx, rbx
0x180001142  call    cs:__imp_?Initialize@WSTRING@@QEAAEPEBGK@Z; WSTRING::Initialize(ushort const *,ulong)
0x180001148  test    al, al
0x18000114a  jnz     loc_1800012ED
0x180001150  mov     rdi, [rsp+360h+arg_8]
0x180001158  mov     rcx, rsi; Block
0x18000115b  call    cs:__imp_free
0x180001161  lea     rcx, [rbp+260h+var_270]
0x180001165  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x18000116b  lea     rcx, [rbp+260h+var_2A0]
0x18000116f  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180001175  movzx   eax, r14b
0x180001179  mov     rcx, [rbp+260h+var_30]
0x180001180  xor     rcx, rsp; StackCookie
0x180001183  call    __security_check_cookie
0x180001188  mov     rbx, [rsp+360h+arg_18]
0x180001190  add     rsp, 340h
0x180001197  pop     r15
0x180001199  pop     r14
0x18000119b  pop     r12
0x18000119d  pop     rsi
0x18000119e  pop     rbp
0x18000119f  retn
0x1800011a0  mov     rdi, rsi
0x1800011a3  mov     [rsp+360h+arg_10], r13
0x1800011ab  cmp     word ptr [rdi], 0
0x1800011af  jz      loc_1800012C5
0x1800011b5  mov     r8d, 0FFFFFFFFh
0x1800011bb  lea     rcx, [rbp+260h+var_270]
0x1800011bf  mov     rdx, rdi
0x1800011c2  call    cs:__imp_?Initialize@WSTRING@@QEAAEPEBGK@Z; WSTRING::Initialize(ushort const *,ulong)
0x1800011c8  test    al, al
0x1800011ca  jz      loc_1800012D0
0x1800011d0  mov     r8d, 104h; nSize
0x1800011d6  mov     [rsp+360h+var_32C], r12d
0x1800011db  lea     rdx, [rbp+260h+Filename]; lpFilename
0x1800011df  xor     ecx, ecx; hModule
0x1800011e1  add     rdi, 14h
0x1800011e5  call    cs:__imp_GetModuleFileNameW
0x1800011eb  cmp     word ptr [rdi], 0
0x1800011ef  lea     rax, [rsp+360h+var_32C]
0x1800011f4  lea     r13, [rbp+260h+Filename]
0x1800011f8  mov     [rsp+360h+var_338], r12d; int
0x1800011fd  cmovnz  r13, rdi
0x180001201  mov     [rsp+360h+var_340], rax; int *
0x180001206  mov     rcx, r13; unsigned __int16 *
0x180001209  lea     r9, [rsp+360h+var_330]; int *
0x18000120e  xor     r8d, r8d; unsigned __int16 *
0x180001211  xor     edx, edx; unsigned __int16 **
0x180001213  call    ?Parse_Cmdline@@YAXPEAGPEAPEAG0PEAH2H@Z; Parse_Cmdline(ushort *,ushort * *,ushort *,int *,int *,int)
0x180001218  movsxd  rcx, [rsp+360h+var_32C]
0x18000121d  mov     ebx, [rsp+360h+var_330]
0x180001221  mov     rax, rcx
0x180001224  not     rax
0x180001227  shr     rax, 3
0x18000122b  cmp     rbx, rax
0x18000122e  jnb     loc_1800012B4
0x180001234  lea     r12d, [rcx+rbx*8]
0x180001238  xor     edx, edx; Flags
0x18000123a  mov     rcx, gs:60h
0x180001243  movsxd  r8, r12d; Size
0x180001246  mov     rcx, [rcx+30h]; HeapHandle
0x18000124a  call    cs:__imp_RtlAllocateHeap
0x180001250  mov     r15, rax
0x180001253  test    rax, rax
0x180001256  jz      loc_180001364
0x18000125c  movsxd  rax, ebx
0x18000125f  lea     r9, [rsp+360h+var_330]; int *
0x180001264  mov     [rsp+360h+var_338], r12d; int
0x180001269  mov     rdx, r15; unsigned __int16 **
0x18000126c  mov     rcx, r13; unsigned __int16 *
0x18000126f  lea     r8, [r15+rax*8]; unsigned __int16 *
0x180001273  lea     rax, [rsp+360h+var_32C]
0x180001278  mov     [rsp+360h+var_340], rax; int *
0x18000127d  call    ?Parse_Cmdline@@YAXPEAGPEAPEAG0PEAH2H@Z; Parse_Cmdline(ushort *,ushort * *,ushort *,int *,int *,int)
0x180001282  mov     ecx, [rsp+360h+var_330]; int
0x180001286  mov     rdx, r15; unsigned __int16 **
0x180001289  call    ?SimulateAutochkMainInvocation@@YAEHPEAPEAG@Z; SimulateAutochkMainInvocation(int,ushort * *)
0x18000128e  mov     rcx, gs:60h
0x180001297  mov     r8, r15; P
0x18000129a  xor     edx, edx; Flags
0x18000129c  movzx   ebx, al
0x18000129f  mov     rcx, [rcx+30h]; HeapHandle
0x1800012a3  call    cs:__imp_RtlFreeHeap
0x1800012a9  test    bl, bl
0x1800012ab  jnz     loc_180001374
0x1800012b1  xor     r12d, r12d
0x1800012b4  movzx   eax, word ptr [rdi]
0x1800012b7  add     rdi, 2
0x1800012bb  test    ax, ax
0x1800012be  jnz     short loc_1800012B4
0x1800012c0  jmp     loc_1800011AB
0x1800012c5  mov     rax, [rsp+360h+var_328]
0x1800012ca  mov     [rax], r14b
0x1800012cd  mov     r14b, 1
0x1800012d0  mov     r13, [rsp+360h+arg_10]
0x1800012d8  jmp     loc_180001150
0x1800012dd  mov     ecx, 8; dwErrCode
0x1800012e2  call    cs:__imp_SetLastError
0x1800012e8  jmp     loc_180001161
0x1800012ed  lea     rcx, [rbp+260h+var_2A0]
0x1800012f1  call    cs:__imp_?QueryChCount@WSTRING@@QEBAKXZ; WSTRING::QueryChCount(void)
0x1800012f7  lea     rcx, [rbp+260h+var_2A0]
0x1800012fb  mov     edi, eax
0x1800012fd  call    cs:__imp_?QueryChCount@WSTRING@@QEBAKXZ; WSTRING::QueryChCount(void)
0x180001303  mov     [rsp+360h+var_338], edi
0x180001307  lea     rdx, [rbp+260h+var_2A0]
0x18000130b  mov     r9d, eax
0x18000130e  mov     dword ptr [rsp+360h+var_340], r12d
0x180001313  xor     r8d, r8d
0x180001316  lea     rcx, [rbp+260h+var_270]
0x18000131a  call    cs:__imp_?Stricmp@WSTRING@@QEBAJPEBV1@KKKK@Z; WSTRING::Stricmp(WSTRING const *,ulong,ulong,ulong,ulong)
0x180001320  test    eax, eax
0x180001322  jnz     short loc_180001358
0x180001324  movzx   eax, word ptr [rbx]
0x180001327  add     rbx, 2
0x18000132b  test    ax, ax
0x18000132e  jnz     short loc_180001324
0x180001330  jmp     loc_18000112F
0x180001335  cmp     eax, 0C0000023h
0x18000133a  jnz     short loc_180001343
0x18000133c  add     ebx, ebx
0x18000133e  jmp     loc_1800010C1
0x180001343  mov     ecx, eax; Status
0x180001345  call    cs:__imp_RtlNtStatusToDosError
0x18000134b  mov     ecx, eax; dwErrCode
0x18000134d  call    cs:__imp_SetLastError
0x180001353  jmp     loc_180001158
0x180001358  mov     byte ptr [r15], 1
0x18000135c  mov     r14b, 1
0x18000135f  jmp     loc_180001150
0x180001364  mov     ecx, 8; dwErrCode
0x180001369  call    cs:__imp_SetLastError
0x18000136f  jmp     loc_1800012B1
0x180001374  mov     rax, [rsp+360h+var_328]
0x180001379  mov     byte ptr [rax], 1
0x18000137c  jmp     loc_1800012CD
```
