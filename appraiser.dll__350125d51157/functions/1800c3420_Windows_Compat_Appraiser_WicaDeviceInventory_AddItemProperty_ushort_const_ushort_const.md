# Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty(ushort const *,ushort const *)

- ea: `0x1800c3420`
- end: `0x1800c37ba`
- name: `?AddItemProperty@WicaDeviceInventory@Appraiser@Compat@Windows@@UEAAJPEBG0@Z`
- size: `922`
- prototype: `int(Windows::Compat::Appraiser::WicaDeviceInventory *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002ebb8`
- `0x1800301d0`
- `0x180083094`
- `0x180083390`
- `0x1800c3420`
- `0x1802174cc`
- `0x18021f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c3646`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c36c7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c3646`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c36c7`
- `KERNEL32!GetProcessHeap` at `0x1800c3459`
- `KERNEL32!GetProcessHeap` at `0x1800c3787`
- `KERNEL32!GetProcessHeap` at `0x1800c3459`
- `KERNEL32!GetProcessHeap` at `0x1800c3787`
- `KERNEL32!HeapFree` at `0x1800c3795`
- `KERNEL32!HeapFree` at `0x1800c3795`

## string_xrefs

- `0x1800c3532`: `onecore\base\appcompat\appraiser\inventory\deviceinventory.cpp`
- `0x1800c3573`: `onecore\base\appcompat\appraiser\inventory\deviceinventory.cpp`
- `0x1800c35e4`: `onecore\base\appcompat\appraiser\inventory\deviceinventory.cpp`
- `0x1800c361f`: `onecore\base\appcompat\appraiser\inventory\deviceinventory.cpp`
- `0x1800c36a9`: `onecore\base\appcompat\appraiser\inventory\deviceinventory.cpp`
- `0x1800c36ee`: `onecore\base\appcompat\appraiser\inventory\deviceinventory.cpp`
- `0x1800c376e`: `onecore\base\appcompat\appraiser\inventory\deviceinventory.cpp`
- `0x1800c3658`: `Failed to create and append properties: [0x%x].`
- `0x1800c373c`: `Failed to create and append properties: [0x%x].`
- `0x1800c3760`: `Failed to create and append properties: [0x%x].`
- `0x1800c35cd`: `Failed to copy and alloc file list: [0x%x].`
- `0x1800c3611`: `Failed to copy and alloc file list: [0x%x].`
- `0x1800c3539`: `Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty`
- `0x1800c356c`: `Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty`
- `0x1800c35dd`: `Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty`
- `0x1800c3618`: `Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty`
- `0x1800c36a2`: `Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty`
- `0x1800c36e7`: `Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty`
- `0x1800c3767`: `Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty`
- `0x1800c3521`: `Failed to copy version string: [%#x].`
- `0x1800c3565`: `Failed to copy version string: [%#x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty(
        Windows::Compat::Appraiser::WicaDeviceInventory *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  wchar_t *v6; // rsi
  unsigned int v7; // ebx
  const wchar_t *v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rdx
  unsigned __int16 *v11; // r8
  unsigned __int16 v12; // cx
  unsigned __int16 *v13; // rcx
  char v14; // dl
  int v15; // eax
  wchar_t *v16; // rbx
  int appended; // eax
  int v18; // eax
  HANDLE ProcessHeap; // rax
  char *v21; // [rsp+20h] [rbp-60h]
  const char *v22; // [rsp+28h] [rbp-58h]
  char *v23; // [rsp+30h] [rbp-50h]
  wchar_t *Context[4]; // [rsp+40h] [rbp-40h] BYREF
  __int128 v25; // [rsp+60h] [rbp-20h]
  __int128 v26; // [rsp+70h] [rbp-10h]
  wchar_t *String; // [rsp+C8h] [rbp+48h] BYREF

  Context[1] = (wchar_t *)-2LL;
  Context[2] = (wchar_t *)GetProcessHeap();
  v26 = 0x10u;
  v25 = 0;
  Context[3] = (wchar_t *)8;
  Context[0] = 0;
  v6 = 0;
  String = 0;
  if ( !*a3 )
    return 0;
  v8 = (const wchar_t *)*((_QWORD *)this + 144);
  if ( !wcscmp_0(L"FileVersion", v8) )
  {
    if ( wcscmp_0(L"Version", a2) )
      return 0;
    v9 = 2147483646;
    v10 = 32;
    v11 = (unsigned __int16 *)((char *)this + 8);
    do
    {
      if ( !v9 )
        break;
      v12 = *a3;
      if ( !*a3 )
        break;
      ++a3;
      *v11++ = v12;
      --v9;
      --v10;
    }
    while ( v10 );
    v7 = v10 == 0 ? 0x8007007A : 0;
    v13 = v11 - 1;
    if ( v10 )
      v13 = v11;
    *v13 = 0;
    if ( v10 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x20Fu,
          "onecore\\base\\appcompat\\appraiser\\inventory\\deviceinventory.cpp",
          "Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty",
          "Failed to copy version string: [%#x].",
          v10 == 0 ? 0x8007007A : 0);
      return 0;
    }
    LODWORD(v23) = -2147024774;
    v22 = "Failed to copy version string: [%#x].";
    v14 = 15;
LABEL_13:
    LODWORD(v21) = v7;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v14,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\deviceinventory.cpp",
      "Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty",
      v21,
      (int)v22,
      v23);
    return v7;
  }
  if ( !wcscmp_0(L"Driver", v8) && !wcscmp_0(L"SYSFILE", a2) )
  {
    v15 = Windows::Compat::Appraiser::Utilities::CopyStringNonConstAlloc(&String, a3);
    v7 = v15;
    if ( v15 < 0 )
    {
      LODWORD(v23) = v15;
      LODWORD(v21) = v15;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        33,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\deviceinventory.cpp",
        "Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty",
        v21,
        (int)"Failed to copy and alloc file list: [0x%x].",
        v23);
      v6 = String;
      goto LABEL_34;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x221u,
        "onecore\\base\\appcompat\\appraiser\\inventory\\deviceinventory.cpp",
        "Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty",
        "Failed to copy and alloc file list: [0x%x].",
        v15);
    Context[0] = 0;
    v6 = String;
    v16 = wcstok_s(String, L",", Context);
    if ( v16 )
    {
      while ( 1 )
      {
        LODWORD(String) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 140) + 8LL))(*((_QWORD *)this + 140));
        appended = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                     a2,
                     v16,
                     (unsigned int *)&String,
                     *((struct Windows::Compat::Appraiser::IPropertyAppender **)this + 140));
        v7 = appended;
        if ( appended < 0 )
          break;
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x22Eu,
            "onecore\\base\\appcompat\\appraiser\\inventory\\deviceinventory.cpp",
            "Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty",
            "Failed to create and append properties: [0x%x].",
            appended);
        v16 = wcstok_s(0, L",", Context);
        if ( !v16 )
          goto LABEL_33;
      }
      LODWORD(v23) = appended;
      LODWORD(v21) = appended;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        46,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\deviceinventory.cpp",
        "Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty",
        v21,
        (int)"Failed to create and append properties: [0x%x].",
        v23);
      goto LABEL_34;
    }
  }
  else
  {
    LODWORD(String) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 140) + 8LL))(*((_QWORD *)this + 140));
    v18 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
            a2,
            a3,
            (unsigned int *)&String,
            *((struct Windows::Compat::Appraiser::IPropertyAppender **)this + 140));
    v7 = v18;
    if ( v18 < 0 )
    {
      LODWORD(v23) = v18;
      v22 = "Failed to create and append properties: [0x%x].";
      v14 = 62;
      goto LABEL_13;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x23Eu,
        "onecore\\base\\appcompat\\appraiser\\inventory\\deviceinventory.cpp",
        "Windows::Compat::Appraiser::WicaDeviceInventory::AddItemProperty",
        "Failed to create and append properties: [0x%x].",
        v18);
  }
LABEL_33:
  v7 = 0;
LABEL_34:
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  return v7;
}

```

## disassembly

```asm
0x1800c3420  mov     rax, rsp
0x1800c3423  push    rbp
0x1800c3424  push    rdi
0x1800c3425  push    r12
0x1800c3427  push    r14
0x1800c3429  push    r15
0x1800c342b  mov     rbp, rsp
0x1800c342e  sub     rsp, 80h
0x1800c3435  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x1800c343d  mov     [rax+8], rbx
0x1800c3441  mov     [rax+10h], rsi
0x1800c3445  mov     rbx, r8
0x1800c3448  mov     r15, rdx
0x1800c344b  mov     r14, rcx
0x1800c344e  xorps   xmm0, xmm0
0x1800c3451  movups  [rbp+var_30], xmm0
0x1800c3455  movups  [rbp+var_10], xmm0
0x1800c3459  call    cs:__imp_GetProcessHeap
0x1800c345f  mov     qword ptr [rbp+var_30], rax
0x1800c3463  mov     qword ptr [rbp+var_10], 10h
0x1800c346b  xorps   xmm0, xmm0
0x1800c346e  movdqu  [rbp+var_20], xmm0
0x1800c3473  xor     r12d, r12d
0x1800c3476  mov     qword ptr [rbp+var_10+8], r12
0x1800c347a  mov     qword ptr [rbp+var_30+8], 8
0x1800c3482  mov     [rbp+Context], r12
0x1800c3486  mov     esi, r12d
0x1800c3489  mov     [rbp+String], r12
0x1800c348d  cmp     r12w, [rbx]
0x1800c3491  jnz     short loc_1800C349B
0x1800c3493  mov     ebx, r12d
0x1800c3496  jmp     loc_1800C379C
0x1800c349b  mov     rdi, [r14+480h]
0x1800c34a2  mov     rdx, rdi; String2
0x1800c34a5  lea     rcx, aFileversion_0; "FileVersion"
0x1800c34ac  call    wcscmp_0
0x1800c34b1  test    eax, eax
0x1800c34b3  jnz     loc_1800C3589
0x1800c34b9  mov     rdx, r15; String2
0x1800c34bc  lea     rcx, aVersion; "Version"
0x1800c34c3  call    wcscmp_0
0x1800c34c8  test    eax, eax
0x1800c34ca  jnz     short loc_1800C3493
0x1800c34cc  mov     eax, 7FFFFFFEh
0x1800c34d1  mov     edx, 20h ; ' '
0x1800c34d6  lea     r8, [r14+8]
0x1800c34da  test    rax, rax
0x1800c34dd  jz      short loc_1800C34FC
0x1800c34df  movzx   ecx, word ptr [rbx]
0x1800c34e2  test    cx, cx
0x1800c34e5  jz      short loc_1800C34FC
0x1800c34e7  add     rbx, 2
0x1800c34eb  mov     [r8], cx
0x1800c34ef  add     r8, 2
0x1800c34f3  dec     rax
0x1800c34f6  sub     rdx, 1
0x1800c34fa  jnz     short loc_1800C34DA
0x1800c34fc  mov     rax, rdx
0x1800c34ff  neg     rax
0x1800c3502  sbb     ebx, ebx
0x1800c3504  not     ebx
0x1800c3506  and     ebx, 8007007Ah
0x1800c350c  lea     rcx, [r8-2]
0x1800c3510  test    rdx, rdx
0x1800c3513  cmovnz  rcx, r8
0x1800c3517  mov     [rcx], r12w
0x1800c351b  jnz     short loc_1800C3553
0x1800c351d  mov     dword ptr [rsp+80h+var_50], ebx; char *
0x1800c3521  lea     r9, aFailedToCopyVe; "Failed to copy version string: [%#x]."
0x1800c3528  mov     qword ptr [rsp+80h+var_58], r9; int
0x1800c352d  mov     edx, 20Fh; bool
0x1800c3532  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c3539  lea     r9, aWindowsCompatA_520; "Windows::Compat::Appraiser::WicaDeviceI"...
0x1800c3540  mov     dword ptr [rsp+80h+var_60], ebx; char *
0x1800c3544  mov     ecx, 1; this
0x1800c3549  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c354e  jmp     loc_1800C379C
0x1800c3553  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c3559  test    al, 1
0x1800c355b  jz      loc_1800C3493
0x1800c3561  mov     dword ptr [rsp+80h+var_60], ebx
0x1800c3565  lea     r9, aFailedToCopyVe; "Failed to copy version string: [%#x]."
0x1800c356c  lea     r8, aWindowsCompatA_520; "Windows::Compat::Appraiser::WicaDeviceI"...
0x1800c3573  lea     rdx, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c357a  mov     ecx, 20Fh; unsigned int
0x1800c357f  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c3584  jmp     loc_1800C3493
0x1800c3589  mov     rdx, rdi; String2
0x1800c358c  lea     rcx, aDriver; "Driver"
0x1800c3593  call    wcscmp_0
0x1800c3598  test    eax, eax
0x1800c359a  jnz     loc_1800C3706
0x1800c35a0  mov     rdx, r15; String2
0x1800c35a3  lea     rcx, aSysfile; "SYSFILE"
0x1800c35aa  call    wcscmp_0
0x1800c35af  test    eax, eax
0x1800c35b1  jnz     loc_1800C3706
0x1800c35b7  mov     rdx, rbx; unsigned __int16 *
0x1800c35ba  lea     rcx, [rbp+String]; unsigned __int16 **
0x1800c35be  call    ?CopyStringNonConstAlloc@Utilities@Appraiser@Compat@Windows@@SAJPEAPEAGPEBG@Z; Windows::Compat::Appraiser::Utilities::CopyStringNonConstAlloc(ushort * *,ushort const *)
0x1800c35c3  mov     ebx, eax
0x1800c35c5  test    eax, eax
0x1800c35c7  jns     short loc_1800C3603
0x1800c35c9  mov     dword ptr [rsp+80h+var_50], eax; char *
0x1800c35cd  lea     r9, aFailedToCopyAn; "Failed to copy and alloc file list: [0x"...
0x1800c35d4  mov     qword ptr [rsp+80h+var_58], r9; int
0x1800c35d9  mov     dword ptr [rsp+80h+var_60], eax; char *
0x1800c35dd  lea     r9, aWindowsCompatA_520; "Windows::Compat::Appraiser::WicaDeviceI"...
0x1800c35e4  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c35eb  mov     edx, 221h; bool
0x1800c35f0  mov     ecx, 1; this
0x1800c35f5  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c35fa  mov     rsi, [rbp+String]
0x1800c35fe  jmp     loc_1800C3782
0x1800c3603  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c3609  test    al, 1
0x1800c360b  jz      short loc_1800C3630
0x1800c360d  mov     dword ptr [rsp+80h+var_60], ebx
0x1800c3611  lea     r9, aFailedToCopyAn; "Failed to copy and alloc file list: [0x"...
0x1800c3618  lea     r8, aWindowsCompatA_520; "Windows::Compat::Appraiser::WicaDeviceI"...
0x1800c361f  lea     rdx, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c3626  mov     ecx, 221h; unsigned int
0x1800c362b  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c3630  mov     [rbp+Context], r12
0x1800c3634  lea     r8, [rbp+Context]; Context
0x1800c3638  lea     rdx, asc_180255EF4; ","
0x1800c363f  mov     rsi, [rbp+String]
0x1800c3643  mov     rcx, rsi; String
0x1800c3646  call    cs:__imp_wcstok_s
0x1800c364c  mov     rbx, rax
0x1800c364f  test    rax, rax
0x1800c3652  jz      loc_1800C377F
0x1800c3658  lea     rdi, aFailedToCreate_50; "Failed to create and append properties:"...
0x1800c365f  mov     rcx, [r14+460h]
0x1800c3666  mov     rdx, [rcx]
0x1800c3669  mov     rax, [rdx+8]
0x1800c366d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3672  mov     dword ptr [rbp+String], eax
0x1800c3675  mov     r9, [r14+460h]; struct Windows::Compat::Appraiser::IPropertyAppender *
0x1800c367c  lea     r8, [rbp+String]; unsigned int *
0x1800c3680  mov     rdx, rbx; unsigned __int16 *
0x1800c3683  mov     rcx, r15; unsigned __int16 *
0x1800c3686  call    ?CreateAndAppendProperty@Utilities@Appraiser@Compat@Windows@@SAJPEBG0PEAKPEAVIPropertyAppender@234@@Z; Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(ushort const *,ushort const *,ulong *,Windows::Compat::Appraiser::IPropertyAppender *)
0x1800c368b  mov     ebx, eax
0x1800c368d  test    eax, eax
0x1800c368f  js      short loc_1800C36DA
0x1800c3691  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c3697  test    al, 1
0x1800c3699  jz      short loc_1800C36BA
0x1800c369b  mov     dword ptr [rsp+80h+var_60], ebx
0x1800c369f  mov     r9, rdi; char *
0x1800c36a2  lea     r8, aWindowsCompatA_520; "Windows::Compat::Appraiser::WicaDeviceI"...
0x1800c36a9  lea     rdx, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c36b0  mov     ecx, 22Eh; unsigned int
0x1800c36b5  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c36ba  lea     r8, [rbp+Context]; Context
0x1800c36be  lea     rdx, asc_180255EF4; ","
0x1800c36c5  xor     ecx, ecx; String
0x1800c36c7  call    cs:__imp_wcstok_s
0x1800c36cd  mov     rbx, rax
0x1800c36d0  test    rax, rax
0x1800c36d3  jnz     short loc_1800C365F
0x1800c36d5  jmp     loc_1800C377F
0x1800c36da  mov     dword ptr [rsp+80h+var_50], ebx; char *
0x1800c36de  mov     qword ptr [rsp+80h+var_58], rdi; int
0x1800c36e3  mov     dword ptr [rsp+80h+var_60], ebx; char *
0x1800c36e7  lea     r9, aWindowsCompatA_520; "Windows::Compat::Appraiser::WicaDeviceI"...
0x1800c36ee  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c36f5  mov     edx, 22Eh; bool
0x1800c36fa  mov     ecx, 1; this
0x1800c36ff  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c3704  jmp     short loc_1800C3782
0x1800c3706  mov     rcx, [r14+460h]
0x1800c370d  mov     rax, [rcx]
0x1800c3710  mov     rax, [rax+8]
0x1800c3714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3719  mov     dword ptr [rbp+String], eax
0x1800c371c  mov     r9, [r14+460h]; struct Windows::Compat::Appraiser::IPropertyAppender *
0x1800c3723  lea     r8, [rbp+String]; unsigned int *
0x1800c3727  mov     rdx, rbx; unsigned __int16 *
0x1800c372a  mov     rcx, r15; unsigned __int16 *
0x1800c372d  call    ?CreateAndAppendProperty@Utilities@Appraiser@Compat@Windows@@SAJPEBG0PEAKPEAVIPropertyAppender@234@@Z; Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(ushort const *,ushort const *,ulong *,Windows::Compat::Appraiser::IPropertyAppender *)
0x1800c3732  mov     ebx, eax
0x1800c3734  test    eax, eax
0x1800c3736  jns     short loc_1800C3752
0x1800c3738  mov     dword ptr [rsp+80h+var_50], eax
0x1800c373c  lea     rdi, aFailedToCreate_50; "Failed to create and append properties:"...
0x1800c3743  mov     qword ptr [rsp+80h+var_58], rdi
0x1800c3748  mov     edx, 23Eh
0x1800c374d  jmp     loc_1800C3532
0x1800c3752  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c3758  test    al, 1
0x1800c375a  jz      short loc_1800C377F
0x1800c375c  mov     dword ptr [rsp+80h+var_60], ebx
0x1800c3760  lea     r9, aFailedToCreate_50; "Failed to create and append properties:"...
0x1800c3767  lea     r8, aWindowsCompatA_520; "Windows::Compat::Appraiser::WicaDeviceI"...
0x1800c376e  lea     rdx, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c3775  mov     ecx, 23Eh; unsigned int
0x1800c377a  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c377f  mov     ebx, r12d
0x1800c3782  test    rsi, rsi
0x1800c3785  jz      short loc_1800C379C
0x1800c3787  call    cs:__imp_GetProcessHeap
0x1800c378d  mov     r8, rsi; lpMem
0x1800c3790  xor     edx, edx; dwFlags
0x1800c3792  mov     rcx, rax; hHeap
0x1800c3795  call    cs:__imp_HeapFree
0x1800c379b  nop
0x1800c379c  mov     eax, ebx
0x1800c379e  lea     r11, [rsp+80h+var_s0]
0x1800c37a6  mov     rbx, [r11+30h]
0x1800c37aa  mov     rsi, [r11+38h]
0x1800c37ae  mov     rsp, r11
0x1800c37b1  pop     r15
0x1800c37b3  pop     r14
0x1800c37b5  pop     r12
0x1800c37b7  pop     rdi
0x1800c37b8  pop     rbp
0x1800c37b9  retn
```
