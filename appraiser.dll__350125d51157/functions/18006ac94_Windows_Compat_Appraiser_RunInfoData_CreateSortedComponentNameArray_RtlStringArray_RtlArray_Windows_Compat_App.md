# Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray(RtlStringArray *,RtlArray<Windows::Compat::Appraiser::ComponentInfo *> *)

- ea: `0x18006ac94`
- end: `0x18006b10e`
- name: `?CreateSortedComponentNameArray@RunInfoData@Appraiser@Compat@Windows@@CAJPEAVRtlStringArray@@PEAV?$RtlArray@PEAUComponentInfo@Appraiser@Compat@Windows@@@@@Z`
- size: `1146`
- prototype: `__int64 __fastcall(RtlStringArray *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006a628`

## callees

- `0x180013e88`
- `0x180013f90`
- `0x1800144c4`
- `0x1800287d4`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18006ac94`
- `0x18006c6d0`
- `0x180082c60`
- `0x18008f784`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18006acca`
- `KERNEL32!GetProcessHeap` at `0x18006ae51`
- `KERNEL32!GetProcessHeap` at `0x18006af3f`
- `KERNEL32!GetProcessHeap` at `0x18006af7a`
- `KERNEL32!GetProcessHeap` at `0x18006afa7`
- `KERNEL32!GetProcessHeap` at `0x18006acca`
- `KERNEL32!GetProcessHeap` at `0x18006ae51`
- `KERNEL32!GetProcessHeap` at `0x18006af3f`
- `KERNEL32!GetProcessHeap` at `0x18006af7a`
- `KERNEL32!GetProcessHeap` at `0x18006afa7`
- `KERNEL32!HeapFree` at `0x18006ae5f`
- `KERNEL32!HeapFree` at `0x18006af34`
- `KERNEL32!HeapFree` at `0x18006af4d`
- `KERNEL32!HeapFree` at `0x18006af88`
- `KERNEL32!HeapFree` at `0x18006af9c`
- `KERNEL32!HeapFree` at `0x18006afb5`
- `KERNEL32!HeapFree` at `0x18006afd3`
- `KERNEL32!HeapFree` at `0x18006b000`
- `KERNEL32!HeapFree` at `0x18006ae5f`
- `KERNEL32!HeapFree` at `0x18006af34`
- `KERNEL32!HeapFree` at `0x18006af4d`
- `KERNEL32!HeapFree` at `0x18006af88`
- `KERNEL32!HeapFree` at `0x18006af9c`
- `KERNEL32!HeapFree` at `0x18006afb5`
- `KERNEL32!HeapFree` at `0x18006afd3`
- `KERNEL32!HeapFree` at `0x18006b000`

## string_xrefs

- `0x18006aded`: `onecore\base\appcompat\appraiser\heads\xml\runinfodata.cpp`
- `0x18006ae37`: `onecore\base\appcompat\appraiser\heads\xml\runinfodata.cpp`
- `0x18006aed1`: `onecore\base\appcompat\appraiser\heads\xml\runinfodata.cpp`
- `0x18006af1a`: `onecore\base\appcompat\appraiser\heads\xml\runinfodata.cpp`
- `0x18006b03e`: `onecore\base\appcompat\appraiser\heads\xml\runinfodata.cpp`
- `0x18006b074`: `onecore\base\appcompat\appraiser\heads\xml\runinfodata.cpp`
- `0x18006b0ae`: `onecore\base\appcompat\appraiser\heads\xml\runinfodata.cpp`
- `0x18006b0e4`: `onecore\base\appcompat\appraiser\heads\xml\runinfodata.cpp`
- `0x18006ade6`: `Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray`
- `0x18006ae30`: `Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray`
- `0x18006aeca`: `Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray`
- `0x18006af13`: `Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray`
- `0x18006b037`: `Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray`
- `0x18006b06d`: `Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray`
- `0x18006b0a7`: `Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray`
- `0x18006b0dd`: `Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray(
        RtlStringArray *this,
        unsigned __int64 *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned __int16 *v6; // rsi
  void *v7; // r14
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // r15
  const unsigned __int16 ***v10; // rdx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  const unsigned __int16 **v13; // rbx
  const unsigned __int16 **v14; // rdi
  const unsigned __int16 *v15; // rbx
  const unsigned __int16 *v16; // rax
  int v17; // eax
  int v18; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rdi
  const unsigned __int16 *v22; // rcx
  int v23; // eax
  int v24; // eax
  HANDLE v25; // rax
  HANDLE v26; // rax
  HANDLE v27; // rax
  char *v29; // [rsp+28h] [rbp-49h]
  const char *v30; // [rsp+38h] [rbp-39h]
  const unsigned __int16 **v31; // [rsp+48h] [rbp-29h]
  HANDLE hHeap[2]; // [rsp+58h] [rbp-19h] BYREF
  __int128 v33; // [rsp+68h] [rbp-9h]
  LPVOID v34[2]; // [rsp+78h] [rbp+7h]
  int v35; // [rsp+88h] [rbp+17h]
  LPVOID lpMem; // [rsp+E0h] [rbp+6Fh] BYREF
  unsigned __int16 *v37; // [rsp+E8h] [rbp+77h] BYREF
  __int64 v38; // [rsp+F0h] [rbp+7Fh] BYREF

  *(_OWORD *)v34 = 0;
  hHeap[0] = GetProcessHeap();
  v34[0] = (LPVOID)16;
  v33 = 0;
  v34[1] = 0;
  hHeap[1] = (HANDLE)16;
  v35 = 0;
  RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(hHeap, v4, v5, 16);
  v38 = 0;
  v6 = 0;
  v37 = 0;
  v7 = 0;
  lpMem = 0;
  RtlStringArray::Clear(this);
  v8 = a2[2];
  if ( v8 )
  {
    v9 = 0;
    while ( 1 )
    {
      v10 = 0;
      if ( v9 < v8 )
      {
        v11 = a2[1] * v9;
        if ( !is_mul_ok(a2[1], v9) || (v12 = a2[5], v10 = (const unsigned __int16 ***)(v12 + v11), v12 + v11 < v12) )
          v10 = 0;
      }
      v13 = *v10;
      v31 = *v10;
      RtlStringArray::Clear((RtlStringArray *)hHeap);
      v14 = v13 + 4;
      (*((void (__fastcall **)(const unsigned __int16 **))v13[4] + 1))(v13 + 4);
      while ( !(*((unsigned int (__fastcall **)(const unsigned __int16 **, __int64 *))*v14 + 2))(v14, &v38) )
      {
        v15 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
        v16 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        v17 = Windows::Compat::Appraiser::Utilities::ConcatenateAlloc((unsigned __int16 **)&lpMem, v15, v16);
        v18 = v17;
        if ( v17 < 0 )
        {
          LODWORD(v30) = v17;
          LODWORD(v29) = v17;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            119,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\runinfodata.cpp",
            "Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray",
            v29,
            (int)"Failed to concatenate strings: [0x%x]",
            v30);
          v7 = lpMem;
          goto LABEL_28;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x377u,
            "onecore\\base\\appcompat\\appraiser\\heads\\xml\\runinfodata.cpp",
            "Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray",
            "Failed to concatenate strings: [0x%x]",
            v17);
        v7 = lpMem;
        v18 = RtlStringArray::Append((RtlStringArray *)hHeap, (const unsigned __int16 *)lpMem, 0);
        if ( v18 < 0 )
        {
          LODWORD(v30) = v18;
          LODWORD(v29) = v18;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            122,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\runinfodata.cpp",
            "Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray",
            v29,
            (int)"Failed to Append: [0x%x]",
            v30);
          goto LABEL_28;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x37Au,
            "onecore\\base\\appcompat\\appraiser\\heads\\xml\\runinfodata.cpp",
            "Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray",
            "Failed to Append: [0x%x]",
            v18);
        if ( v7 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v7);
          v7 = 0;
          lpMem = 0;
        }
      }
      RtlStringArray::Sort((RtlStringArray *)hHeap);
      v20 = RtlStringArray::AllocMultiString((RtlStringArray *)hHeap);
      v21 = v20;
      if ( !v20 )
        break;
      Windows::Compat::Appraiser::Utilities::MultiStringToSingleString(v20);
      v23 = Windows::Compat::Appraiser::Utilities::ConcatenateAlloc(&v37, *v31, v22);
      v18 = v23;
      if ( v23 < 0 )
      {
        LODWORD(v30) = v23;
        LODWORD(v29) = v23;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          139,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\runinfodata.cpp",
          "Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray",
          v29,
          (int)"Failed to concatenate strings: [0x%x]",
          v30);
        v6 = v37;
        goto LABEL_29;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x38Bu,
          "onecore\\base\\appcompat\\appraiser\\heads\\xml\\runinfodata.cpp",
          "Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray",
          "Failed to concatenate strings: [0x%x]",
          v23);
      v6 = v37;
      v24 = RtlStringArray::Append(this, v37, 0);
      v18 = v24;
      if ( v24 < 0 )
      {
        LODWORD(v30) = v24;
        LODWORD(v29) = v24;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          142,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\runinfodata.cpp",
          "Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray",
          v29,
          (int)"Failed to Append: [0x%x]",
          v30);
        goto LABEL_29;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x38Eu,
          "onecore\\base\\appcompat\\appraiser\\heads\\xml\\runinfodata.cpp",
          "Windows::Compat::Appraiser::RunInfoData::CreateSortedComponentNameArray",
          "Failed to Append: [0x%x]",
          v24);
      HeapFree(hHeap[0], 0, v21);
      if ( v6 )
      {
        v25 = GetProcessHeap();
        HeapFree(v25, 0, v6);
        v6 = 0;
        v37 = 0;
      }
      ++v9;
      v8 = a2[2];
      if ( v9 >= v8 )
        goto LABEL_27;
    }
    v18 = -2147024882;
  }
  else
  {
LABEL_27:
    RtlStringArray::Sort(this);
    v18 = 0;
LABEL_28:
    v21 = 0;
  }
LABEL_29:
  if ( v7 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v7);
  }
  if ( v21 )
    HeapFree(hHeap[0], 0, v21);
  if ( v6 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v6);
  }
  RtlStringArray::Clear((RtlStringArray *)hHeap);
  if ( v34[1] )
    HeapFree(hHeap[0], 0, v34[1]);
  *(_OWORD *)hHeap = 0;
  v33 = 0;
  *(_OWORD *)v34 = 0;
  RtlStringArray::Clear((RtlStringArray *)hHeap);
  if ( v34[1] )
    HeapFree(hHeap[0], 0, v34[1]);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18006ac94  mov     rax, rsp
0x18006ac97  push    rbp
0x18006ac98  push    rsi
0x18006ac99  push    rdi
0x18006ac9a  push    r12
0x18006ac9c  push    r13
0x18006ac9e  push    r14
0x18006aca0  push    r15
0x18006aca2  lea     rbp, [rax-5Fh]
0x18006aca6  sub     rsp, 90h
0x18006acad  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x18006acb5  mov     [rax+8], rbx
0x18006acb9  mov     r13, rdx
0x18006acbc  mov     r12, rcx
0x18006acbf  xorps   xmm0, xmm0
0x18006acc2  movups  xmmword ptr [rbp+57h+hHeap], xmm0
0x18006acc6  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18006acca  call    cs:__imp_GetProcessHeap
0x18006acd0  mov     [rbp+57h+hHeap], rax
0x18006acd4  mov     r9d, 10h
0x18006acda  mov     [rbp+57h+var_50], r9
0x18006acde  xorps   xmm0, xmm0
0x18006ace1  movdqu  [rbp+57h+var_60], xmm0
0x18006ace6  mov     [rbp+57h+var_50+8], 0
0x18006acee  mov     [rbp+57h+hHeap+8], r9
0x18006acf2  mov     [rbp+57h+var_40], 0
0x18006acf9  lea     rcx, [rbp+57h+hHeap]
0x18006acfd  call    ?Initialize@?$RtlArray@URTL_STRING_ITEM@RtlStringArray@@@@QEAAJPEAX_K1H@Z; RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x18006ad02  nop
0x18006ad03  mov     [rbp+57h+arg_18], 0
0x18006ad0b  xor     esi, esi
0x18006ad0d  mov     [rbp+57h+arg_10], rsi
0x18006ad11  xor     r14d, r14d
0x18006ad14  mov     [rbp+57h+lpMem], r14
0x18006ad18  mov     rcx, r12; this
0x18006ad1b  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x18006ad20  mov     rax, [r13+10h]
0x18006ad24  test    rax, rax
0x18006ad27  jz      loc_18006AF69
0x18006ad2d  xor     r15d, r15d
0x18006ad30  xor     edx, edx
0x18006ad32  cmp     r15, rax
0x18006ad35  jnb     short loc_18006AD56
0x18006ad37  mov     [rbp+57h+var_80], rdx
0x18006ad3b  mov     rax, r15
0x18006ad3e  mul     qword ptr [r13+8]
0x18006ad42  test    rdx, rdx
0x18006ad45  jnz     short loc_18006AD54
0x18006ad47  mov     rcx, [r13+28h]
0x18006ad4b  lea     rdx, [rcx+rax]
0x18006ad4f  cmp     rdx, rcx
0x18006ad52  jnb     short loc_18006AD56
0x18006ad54  xor     edx, edx
0x18006ad56  mov     rbx, [rdx]
0x18006ad59  mov     [rbp+57h+var_80], rbx
0x18006ad5d  lea     rcx, [rbp+57h+hHeap]; this
0x18006ad61  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x18006ad66  lea     rdi, [rbx+20h]
0x18006ad6a  mov     rax, [rdi]
0x18006ad6d  mov     rcx, rdi
0x18006ad70  mov     rax, [rax+8]
0x18006ad74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad79  mov     rax, [rdi]
0x18006ad7c  lea     rdx, [rbp+57h+arg_18]
0x18006ad80  mov     rcx, rdi
0x18006ad83  mov     rax, [rax+10h]
0x18006ad87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad8c  test    eax, eax
0x18006ad8e  jnz     loc_18006AE71
0x18006ad94  mov     rcx, [rbp+57h+arg_18]
0x18006ad98  mov     rax, [rcx]
0x18006ad9b  mov     rax, [rax+8]
0x18006ad9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ada4  mov     rbx, rax
0x18006ada7  mov     rcx, [rbp+57h+arg_18]
0x18006adab  mov     rdx, [rcx]
0x18006adae  mov     rax, [rdx+10h]
0x18006adb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006adb7  mov     r8, rax; unsigned __int16 *
0x18006adba  mov     rdx, rbx; unsigned __int16 *
0x18006adbd  lea     rcx, [rbp+57h+lpMem]; unsigned __int16 **
0x18006adc1  call    ?ConcatenateAlloc@Utilities@Appraiser@Compat@Windows@@SAJPEAPEAGPEBG1@Z; Windows::Compat::Appraiser::Utilities::ConcatenateAlloc(ushort * *,ushort const *,ushort const *)
0x18006adc6  mov     ebx, eax
0x18006adc8  test    eax, eax
0x18006adca  js      loc_18006B059
0x18006add0  mov     ecx, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18006add6  test    cl, 1
0x18006add9  jz      short loc_18006ADFE
0x18006addb  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18006addf  lea     r9, aFailedToConcat_5; "Failed to concatenate strings: [0x%x]"
0x18006ade6  lea     r8, aWindowsCompatA_8; "Windows::Compat::Appraiser::RunInfoData"...
0x18006aded  lea     rdx, aOnecoreBaseApp_96; "onecore\\base\\appcompat\\appraiser\\he"...
0x18006adf4  mov     ecx, 377h; unsigned int
0x18006adf9  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18006adfe  xor     r8d, r8d; unsigned __int64
0x18006ae01  mov     r14, [rbp+57h+lpMem]
0x18006ae05  mov     rdx, r14; unsigned __int16 *
0x18006ae08  lea     rcx, [rbp+57h+hHeap]; this
0x18006ae0c  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x18006ae11  mov     ebx, eax
0x18006ae13  test    eax, eax
0x18006ae15  js      loc_18006B023
0x18006ae1b  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18006ae21  test    al, 1
0x18006ae23  jz      short loc_18006AE48
0x18006ae25  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18006ae29  lea     r9, aFailedToAppend_17; "Failed to Append: [0x%x]"
0x18006ae30  lea     r8, aWindowsCompatA_8; "Windows::Compat::Appraiser::RunInfoData"...
0x18006ae37  lea     rdx, aOnecoreBaseApp_96; "onecore\\base\\appcompat\\appraiser\\he"...
0x18006ae3e  mov     ecx, 37Ah; unsigned int
0x18006ae43  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18006ae48  test    r14, r14
0x18006ae4b  jz      loc_18006AD79
0x18006ae51  call    cs:__imp_GetProcessHeap
0x18006ae57  mov     r8, r14; lpMem
0x18006ae5a  xor     edx, edx; dwFlags
0x18006ae5c  mov     rcx, rax; hHeap
0x18006ae5f  call    cs:__imp_HeapFree
0x18006ae65  xor     r14d, r14d
0x18006ae68  mov     [rbp+57h+lpMem], r14
0x18006ae6c  jmp     loc_18006AD79
0x18006ae71  lea     rcx, [rbp+57h+hHeap]; this
0x18006ae75  call    ?Sort@RtlStringArray@@QEAAXXZ; RtlStringArray::Sort(void)
0x18006ae7a  lea     rcx, [rbp+57h+hHeap]; this
0x18006ae7e  call    ?AllocMultiString@RtlStringArray@@QEAAPEAGXZ; RtlStringArray::AllocMultiString(void)
0x18006ae83  mov     rdi, rax
0x18006ae86  test    rax, rax
0x18006ae89  jz      loc_18006B103
0x18006ae8f  mov     rcx, rax; unsigned __int16 *
0x18006ae92  call    ?MultiStringToSingleString@Utilities@Appraiser@Compat@Windows@@SAXPEAG@Z; Windows::Compat::Appraiser::Utilities::MultiStringToSingleString(ushort *)
0x18006ae97  mov     r8, rcx; unsigned __int16 *
0x18006ae9a  mov     rdx, [rbp+57h+var_80]
0x18006ae9e  mov     rdx, [rdx]; unsigned __int16 *
0x18006aea1  lea     rcx, [rbp+57h+arg_10]; unsigned __int16 **
0x18006aea5  call    ?ConcatenateAlloc@Utilities@Appraiser@Compat@Windows@@SAJPEAPEAGPEBG1@Z; Windows::Compat::Appraiser::Utilities::ConcatenateAlloc(ushort * *,ushort const *,ushort const *)
0x18006aeaa  mov     ebx, eax
0x18006aeac  test    eax, eax
0x18006aeae  js      loc_18006B0C9
0x18006aeb4  mov     ecx, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18006aeba  test    cl, 1
0x18006aebd  jz      short loc_18006AEE2
0x18006aebf  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18006aec3  lea     r9, aFailedToConcat_5; "Failed to concatenate strings: [0x%x]"
0x18006aeca  lea     r8, aWindowsCompatA_8; "Windows::Compat::Appraiser::RunInfoData"...
0x18006aed1  lea     rdx, aOnecoreBaseApp_96; "onecore\\base\\appcompat\\appraiser\\he"...
0x18006aed8  mov     ecx, 38Bh; unsigned int
0x18006aedd  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18006aee2  xor     r8d, r8d; unsigned __int64
0x18006aee5  mov     rsi, [rbp+57h+arg_10]
0x18006aee9  mov     rdx, rsi; unsigned __int16 *
0x18006aeec  mov     rcx, r12; this
0x18006aeef  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x18006aef4  mov     ebx, eax
0x18006aef6  test    eax, eax
0x18006aef8  js      loc_18006B093
0x18006aefe  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18006af04  test    al, 1
0x18006af06  jz      short loc_18006AF2B
0x18006af08  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18006af0c  lea     r9, aFailedToAppend_17; "Failed to Append: [0x%x]"
0x18006af13  lea     r8, aWindowsCompatA_8; "Windows::Compat::Appraiser::RunInfoData"...
0x18006af1a  lea     rdx, aOnecoreBaseApp_96; "onecore\\base\\appcompat\\appraiser\\he"...
0x18006af21  mov     ecx, 38Eh; unsigned int
0x18006af26  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18006af2b  mov     r8, rdi; lpMem
0x18006af2e  xor     edx, edx; dwFlags
0x18006af30  mov     rcx, [rbp+57h+hHeap]; hHeap
0x18006af34  call    cs:__imp_HeapFree
0x18006af3a  test    rsi, rsi
0x18006af3d  jz      short loc_18006AF59
0x18006af3f  call    cs:__imp_GetProcessHeap
0x18006af45  mov     r8, rsi; lpMem
0x18006af48  xor     edx, edx; dwFlags
0x18006af4a  mov     rcx, rax; hHeap
0x18006af4d  call    cs:__imp_HeapFree
0x18006af53  xor     esi, esi
0x18006af55  mov     [rbp+57h+arg_10], rsi
0x18006af59  inc     r15
0x18006af5c  mov     rax, [r13+10h]
0x18006af60  cmp     r15, rax
0x18006af63  jb      loc_18006AD30
0x18006af69  mov     rcx, r12; this
0x18006af6c  call    ?Sort@RtlStringArray@@QEAAXXZ; RtlStringArray::Sort(void)
0x18006af71  xor     ebx, ebx
0x18006af73  xor     edi, edi
0x18006af75  test    r14, r14
0x18006af78  jz      short loc_18006AF8E
0x18006af7a  call    cs:__imp_GetProcessHeap
0x18006af80  mov     r8, r14; lpMem
0x18006af83  xor     edx, edx; dwFlags
0x18006af85  mov     rcx, rax; hHeap
0x18006af88  call    cs:__imp_HeapFree
0x18006af8e  test    rdi, rdi
0x18006af91  jz      short loc_18006AFA2
0x18006af93  mov     r8, rdi; lpMem
0x18006af96  xor     edx, edx; dwFlags
0x18006af98  mov     rcx, [rbp+57h+hHeap]; hHeap
0x18006af9c  call    cs:__imp_HeapFree
0x18006afa2  test    rsi, rsi
0x18006afa5  jz      short loc_18006AFBB
0x18006afa7  call    cs:__imp_GetProcessHeap
0x18006afad  mov     r8, rsi; lpMem
0x18006afb0  xor     edx, edx; dwFlags
0x18006afb2  mov     rcx, rax; hHeap
0x18006afb5  call    cs:__imp_HeapFree
0x18006afbb  lea     rcx, [rbp+57h+hHeap]; this
0x18006afbf  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x18006afc4  mov     r8, [rbp+57h+var_50+8]; lpMem
0x18006afc8  test    r8, r8
0x18006afcb  jz      short loc_18006AFD9
0x18006afcd  xor     edx, edx; dwFlags
0x18006afcf  mov     rcx, [rbp+57h+hHeap]; hHeap
0x18006afd3  call    cs:__imp_HeapFree
0x18006afd9  xorps   xmm0, xmm0
0x18006afdc  movups  xmmword ptr [rbp+57h+hHeap], xmm0
0x18006afe0  movups  [rbp+57h+var_60], xmm0
0x18006afe4  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18006afe8  lea     rcx, [rbp+57h+hHeap]; this
0x18006afec  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x18006aff1  mov     r8, [rbp+57h+var_50+8]; lpMem
0x18006aff5  test    r8, r8
0x18006aff8  jz      short loc_18006B006
0x18006affa  xor     edx, edx; dwFlags
0x18006affc  mov     rcx, [rbp+57h+hHeap]; hHeap
0x18006b000  call    cs:__imp_HeapFree
0x18006b006  mov     eax, ebx
0x18006b008  mov     rbx, [rsp+0C0h+arg_0]
0x18006b010  add     rsp, 90h
0x18006b017  pop     r15
0x18006b019  pop     r14
0x18006b01b  pop     r13
0x18006b01d  pop     r12
0x18006b01f  pop     rdi
0x18006b020  pop     rsi
0x18006b021  pop     rbp
0x18006b022  retn
0x18006b023  mov     [rsp+30h], ebx; char *
0x18006b027  lea     rax, aFailedToAppend_17; "Failed to Append: [0x%x]"
0x18006b02e  mov     qword ptr [rsp+0C0h+var_98], rax; int
0x18006b033  mov     dword ptr [rsp+0C0h+var_A0], ebx; char *
0x18006b037  lea     r9, aWindowsCompatA_8; "Windows::Compat::Appraiser::RunInfoData"...
0x18006b03e  lea     r8, aOnecoreBaseApp_96; "onecore\\base\\appcompat\\appraiser\\he"...
0x18006b045  mov     edx, 37Ah; bool
0x18006b04a  mov     ecx, 1; this
0x18006b04f  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18006b054  jmp     loc_18006AF73
0x18006b059  mov     [rsp+30h], ebx; char *
0x18006b05d  lea     rax, aFailedToConcat_5; "Failed to concatenate strings: [0x%x]"
0x18006b064  mov     qword ptr [rsp+0C0h+var_98], rax; int
0x18006b069  mov     dword ptr [rsp+0C0h+var_A0], ebx; char *
0x18006b06d  lea     r9, aWindowsCompatA_8; "Windows::Compat::Appraiser::RunInfoData"...
0x18006b074  lea     r8, aOnecoreBaseApp_96; "onecore\\base\\appcompat\\appraiser\\he"...
0x18006b07b  mov     edx, 377h; bool
0x18006b080  mov     ecx, 1; this
0x18006b085  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18006b08a  mov     r14, [rbp+57h+lpMem]
0x18006b08e  jmp     loc_18006AF73
0x18006b093  mov     [rsp+30h], ebx; char *
0x18006b097  lea     rax, aFailedToAppend_17; "Failed to Append: [0x%x]"
0x18006b09e  mov     qword ptr [rsp+0C0h+var_98], rax; int
0x18006b0a3  mov     dword ptr [rsp+0C0h+var_A0], ebx; char *
0x18006b0a7  lea     r9, aWindowsCompatA_8; "Windows::Compat::Appraiser::RunInfoData"...
0x18006b0ae  lea     r8, aOnecoreBaseApp_96; "onecore\\base\\appcompat\\appraiser\\he"...
0x18006b0b5  mov     edx, 38Eh; bool
0x18006b0ba  mov     ecx, 1; this
0x18006b0bf  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18006b0c4  jmp     loc_18006AF75
0x18006b0c9  mov     [rsp+30h], ebx; char *
0x18006b0cd  lea     rax, aFailedToConcat_5; "Failed to concatenate strings: [0x%x]"
0x18006b0d4  mov     qword ptr [rsp+0C0h+var_98], rax; int
0x18006b0d9  mov     dword ptr [rsp+0C0h+var_A0], ebx; char *
0x18006b0dd  lea     r9, aWindowsCompatA_8; "Windows::Compat::Appraiser::RunInfoData"...
0x18006b0e4  lea     r8, aOnecoreBaseApp_96; "onecore\\base\\appcompat\\appraiser\\he"...
0x18006b0eb  mov     edx, 38Bh; bool
0x18006b0f0  mov     ecx, 1; this
0x18006b0f5  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18006b0fa  mov     rsi, [rbp+57h+arg_10]
0x18006b0fe  jmp     loc_18006AF75
0x18006b103  mov     ebx, 8007000Eh
0x18006b108  jmp     loc_18006AF75
```
