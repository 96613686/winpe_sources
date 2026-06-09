# AslPathWildcardFindFirst

- ea: `0x18001cac8`
- end: `0x18001d028`
- name: `AslPathWildcardFindFirst`
- size: `1376`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, loader_planting`

## callers

- `0x1801b73d0`

## callees

- `0x1800092dc`
- `0x18001722c`
- `0x1800186c4`
- `0x18001a2f4`
- `0x18001c23c`
- `0x18001cac8`
- `0x18001d030`
- `0x18001dbd8`
- `0x18001dff0`
- `0x18001e0d8`
- `0x18001e138`
- `0x1802174d8`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18001cfc5`
- `ntdll!RtlFreeUnicodeString` at `0x18001cfc5`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18001cb58`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18001cb58`
- `ntdll!RtlFreeHeap` at `0x18001cfe4`
- `ntdll!RtlFreeHeap` at `0x18001cfe4`
- `ntdll!RtlAllocateHeap` at `0x18001cbc9`
- `ntdll!RtlAllocateHeap` at `0x18001cce8`
- `ntdll!RtlAllocateHeap` at `0x18001cbc9`
- `ntdll!RtlAllocateHeap` at `0x18001cce8`
- `ntdll!RtlInitUnicodeString` at `0x18001cdbb`
- `ntdll!RtlInitUnicodeString` at `0x18001cdbb`
- `KERNEL32!HeapReAlloc` at `0x18001cefe`
- `KERNEL32!HeapReAlloc` at `0x18001cefe`
- `KERNEL32!GetProcessHeap` at `0x18001cd32`
- `KERNEL32!GetProcessHeap` at `0x18001cd32`
- `KERNEL32!HeapAlloc` at `0x18001cd8d`
- `KERNEL32!HeapAlloc` at `0x18001cedd`
- `KERNEL32!HeapAlloc` at `0x18001cd8d`
- `KERNEL32!HeapAlloc` at `0x18001cedd`
- `KERNEL32!HeapFree` at `0x18001ce1a`
- `KERNEL32!HeapFree` at `0x18001ce1a`

## string_xrefs

- `0x18001ce44`: `AslpPathWildcardInitStack`
- `0x18001cb68`: `Failed to convert dos path to nt path [%x]`
- `0x18001cc63`: `AslPathWildcardFindFirst`
- `0x18001cfb5`: `AslPathWildcardFindFirst`
- `0x18001cb8d`: `AslPathCleanUstr failed [%x]`
- `0x18001ccc0`: `RtlStringCbCopyNW failed [%x]`
- `0x18001cc56`: `Failed to split the wildcard path`
- `0x18001ce52`: `AslpPathWildcardInitStack failed [%x]`
- `0x18001cded`: `AslpPathWildcardAllocMatchNode failed to create root of path [%x]`
- `0x18001cf78`: `AslpPathWildcardPushNode failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindFirst(_WORD *a1, void *a2, const wchar_t *a3, __int64 *a4)
{
  WCHAR *v8; // r15
  int v9; // eax
  signed int v10; // ebx
  int v11; // eax
  unsigned __int16 v12; // ax
  unsigned __int64 v13; // rdi
  WCHAR *Heap; // rax
  unsigned __int64 v15; // rdi
  WCHAR *v16; // rdx
  PWSTR Buffer; // rcx
  unsigned __int64 v18; // rax
  WCHAR *v19; // rcx
  int Leaves; // eax
  WCHAR *v21; // rcx
  signed int Next; // eax
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // rdi
  HANDLE ProcessHeap; // rax
  void *v27; // rax
  void *v28; // rbx
  int matched; // eax
  void *v30; // r8
  unsigned __int64 v31; // r13
  unsigned __int64 v32; // rcx
  __int64 v33; // rbx
  unsigned __int64 v34; // rbx
  unsigned __int128 v35; // rax
  void *v36; // r8
  void *v37; // rcx
  void *v38; // rax
  LPVOID v39; // r14
  _OWORD *v40; // rax
  __int64 v41; // [rsp+20h] [rbp-60h]
  size_t Size; // [rsp+30h] [rbp-50h]
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-38h] BYREF
  __int128 v45; // [rsp+58h] [rbp-28h] BYREF
  __int128 v46; // [rsp+68h] [rbp-18h]
  PVOID v48; // [rsp+C8h] [rbp+48h] BYREF

  v48 = a2;
  if ( !a1 )
    return 3221225711LL;
  if ( !a3 || !*a3 )
    return 3221225713LL;
  if ( !a4 )
    return 3221225714LL;
  *a4 = 0;
  *a1 = 0;
  v48 = 0;
  v8 = 0;
  UnicodeString = 0;
  DestinationString = 0;
  v45 = 0;
  v46 = 0;
  v9 = RtlDosPathNameToNtPathName_U_WithStatus(a3, &UnicodeString, 0, 0);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v11 = AslPathCleanUstr(&UnicodeString);
    v10 = v11;
    if ( v11 < 0 )
    {
      AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2257, "AslPathCleanUstr failed [%x]", v11);
      goto LABEL_66;
    }
    v12 = UnicodeString.Length + 4;
    if ( (unsigned __int16)(UnicodeString.Length + 4) < UnicodeString.Length )
    {
      v10 = -1073741675;
      v24 = "RtlUShortAdd failed [%x]";
      LODWORD(v41) = -1073741675;
      v23 = 2263;
      goto LABEL_65;
    }
    v13 = v12;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v12);
    v8 = Heap;
    if ( !Heap )
    {
LABEL_13:
      v10 = -1073741801;
      goto LABEL_66;
    }
    v15 = v13 >> 1;
    if ( v15 )
    {
      v16 = Heap;
      Buffer = UnicodeString.Buffer;
      v18 = (unsigned __int64)UnicodeString.Length >> 1;
      do
      {
        if ( !v18 )
          break;
        if ( !*Buffer )
          break;
        *v16++ = *Buffer++;
        --v18;
        --v15;
      }
      while ( v15 );
      v19 = v16 - 1;
      v10 = v15 == 0 ? 0x80000005 : 0;
      if ( v15 )
        v19 = v16;
      *v19 = 0;
      if ( v15 )
      {
        Leaves = AslpPathWildcardMakeLeaves(v8);
        if ( !Leaves )
        {
          v10 = -1073741767;
          AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2293, "Failed to split the wildcard path");
          goto LABEL_66;
        }
        if ( Leaves == 1 )
        {
          v21 = UnicodeString.Buffer;
          *a4 = -1;
          if ( !(unsigned int)AslDoesFileExistNtPath(v21) )
          {
            v10 = -2147483642;
            goto LABEL_66;
          }
          v10 = RtlStringCchCopyW(a1, 260, a3);
          Next = 0;
          if ( v10 < 0 )
          {
            v23 = 2311;
LABEL_29:
            v24 = "RtlStringCbCopyNW failed [%x]";
LABEL_30:
            LODWORD(v41) = v10;
LABEL_65:
            AslLogCallPrintf(1, "AslPathWildcardFindFirst", v23, v24, v41);
            goto LABEL_66;
          }
LABEL_58:
          v10 = Next;
          goto LABEL_66;
        }
        v48 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x40u);
        v25 = (__int64)v48;
        if ( !v48 )
          goto LABEL_13;
        *(_DWORD *)v25 = wcsncmp_0(a3, L"\\??\\", 4u) != 0;
        *(_QWORD *)(v25 + 8) = v8;
        v8 = 0;
        *(_OWORD *)(v25 + 16) = 0;
        *(_OWORD *)(v25 + 32) = 0;
        *(_OWORD *)(v25 + 48) = 0;
        ProcessHeap = GetProcessHeap();
        *(_QWORD *)(v25 + 32) = 0;
        *(_QWORD *)(v25 + 16) = ProcessHeap;
        *(_QWORD *)(v25 + 48) = 16;
        *(_QWORD *)(v25 + 40) = 0;
        *(_QWORD *)(v25 + 56) = 0;
        *(_QWORD *)(v25 + 24) = 32;
        if ( is_mul_ok(0, 0x20u) && is_mul_ok(0x10u, 0x20u) )
        {
          v27 = HeapAlloc(ProcessHeap, (0x10 * (unsigned __int128)0x20u) >> 64, 0x200u);
          v28 = v27;
          if ( v27 )
          {
            memset_0(v27, 0, 0x200u);
            *(_QWORD *)(v25 + 56) = v28;
            *(_QWORD *)(v25 + 40) = 16;
            RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v25 + 8));
            matched = AslpPathWildcardAllocMatchNode(
                        (unsigned int)&v45,
                        (unsigned int)&DestinationString,
                        *(_QWORD *)(v25 + 8),
                        1,
                        0,
                        0);
            v10 = matched;
            if ( matched < 0 )
            {
              LODWORD(v41) = matched;
              AslLogCallPrintf(
                1,
                "AslPathWildcardFindFirst",
                2362,
                "AslpPathWildcardAllocMatchNode failed to create root of path [%x]",
                v41);
              goto LABEL_66;
            }
            v31 = *(_QWORD *)(v25 + 32);
            if ( v31 >= *(_QWORD *)(v25 + 40) )
            {
              v32 = v31 + 1;
              if ( v31 + 1 <= *(_QWORD *)(v25 + 40) )
              {
                v10 = -2147024809;
                goto LABEL_61;
              }
              v33 = *(_QWORD *)(v25 + 48) - 1LL;
              if ( v33 + v32 < v32
                || !is_mul_ok(*(_QWORD *)(v25 + 40), *(_QWORD *)(v25 + 24))
                || (v34 = (v33 + v32) & ~v33,
                    v35 = v34 * (unsigned __int128)*(unsigned __int64 *)(v25 + 24),
                    Size = v34 * *(_QWORD *)(v25 + 24),
                    !is_mul_ok(v34, *(_QWORD *)(v25 + 24))) )
              {
                v10 = -2147483637;
                goto LABEL_61;
              }
              v36 = *(void **)(v25 + 56);
              v37 = *(void **)(v25 + 16);
              if ( v36 )
              {
                v39 = HeapReAlloc(v37, DWORD2(v35), v36, v35);
              }
              else
              {
                v38 = HeapAlloc(v37, DWORD2(v35), v35);
                v39 = v38;
                if ( v38 )
                  memset_0(v38, 0, Size);
              }
              if ( !v39 )
              {
                v10 = -2147024882;
                goto LABEL_61;
              }
              *(_QWORD *)(v25 + 56) = v39;
              *(_QWORD *)(v25 + 40) = v34;
            }
            if ( is_mul_ok(*(_QWORD *)(v25 + 24), v31) )
            {
              v40 = (_OWORD *)(*(_QWORD *)(v25 + 56) + *(_QWORD *)(v25 + 24) * v31);
              if ( (unsigned __int64)v40 >= *(_QWORD *)(v25 + 56) )
              {
                *v40 = v45;
                v40[1] = v46;
                ++*(_QWORD *)(v25 + 32);
                *a4 = v25;
                v45 = 0;
                v46 = 0;
                Next = AslPathWildcardFindNext(a1, 260, v25);
                goto LABEL_58;
              }
            }
            v10 = -2147483637;
LABEL_61:
            v24 = "AslpPathWildcardPushNode failed [%x]";
            v23 = 2368;
            goto LABEL_30;
          }
          v10 = -2147024882;
        }
        else
        {
          v10 = -2147483637;
        }
        v30 = *(void **)(v25 + 56);
        if ( v30 )
          HeapFree(*(HANDLE *)(v25 + 16), 0, v30);
        *(_OWORD *)(v25 + 16) = 0;
        *(_OWORD *)(v25 + 32) = 0;
        *(_OWORD *)(v25 + 48) = 0;
        AslLogCallPrintf(1, "AslpPathWildcardInitStack", 2148, "RtlArrayInitialize failed [%x]", v10);
        v24 = "AslpPathWildcardInitStack failed [%x]";
        v23 = 2349;
        goto LABEL_30;
      }
    }
    else
    {
      v10 = -1073741811;
    }
    v23 = 2275;
    goto LABEL_29;
  }
  AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2246, "Failed to convert dos path to nt path [%x]", v9);
LABEL_66:
  RtlFreeUnicodeString(&UnicodeString);
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  if ( v10 < 0 )
  {
    AslpPathWildcardFreeFindContext(&v48);
    AslpPathWildcardFreeMatchNode(&v45);
    *a4 = 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001cac8  mov     [rsp-38h+arg_10], rbx
0x18001cacd  mov     [rsp-38h+arg_8], rdx
0x18001cad2  mov     [rsp-38h+arg_0], rcx
0x18001cad7  push    rbp
0x18001cad8  push    rsi
0x18001cad9  push    rdi
0x18001cada  push    r12
0x18001cadc  push    r13
0x18001cade  push    r14
0x18001cae0  push    r15
0x18001cae2  mov     rbp, rsp
0x18001cae5  sub     rsp, 80h
0x18001caec  xor     eax, eax
0x18001caee  mov     r12, r9
0x18001caf1  mov     r14, r8
0x18001caf4  mov     r13, rcx
0x18001caf7  test    rcx, rcx
0x18001cafa  jnz     short loc_18001CB06
0x18001cafc  mov     eax, 0C00000EFh
0x18001cb01  jmp     loc_18001D00D
0x18001cb06  test    r14, r14
0x18001cb09  jz      loc_18001D008
0x18001cb0f  cmp     [r8], ax
0x18001cb13  jz      loc_18001D008
0x18001cb19  test    r12, r12
0x18001cb1c  jnz     short loc_18001CB28
0x18001cb1e  mov     eax, 0C00000F2h
0x18001cb23  jmp     loc_18001D00D
0x18001cb28  xorps   xmm0, xmm0
0x18001cb2b  mov     [r9], rax
0x18001cb2e  xorps   xmm1, xmm1
0x18001cb31  mov     [rcx], ax
0x18001cb34  xor     r9d, r9d
0x18001cb37  mov     [rbp+arg_8], rax
0x18001cb3b  mov     rcx, r14
0x18001cb3e  lea     rdx, [rbp+UnicodeString]
0x18001cb42  xor     r8d, r8d
0x18001cb45  mov     r15, rax
0x18001cb48  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x18001cb4c  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x18001cb50  movups  [rbp+var_28], xmm0
0x18001cb54  movups  [rbp+var_18], xmm0
0x18001cb58  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18001cb5e  mov     ebx, eax
0x18001cb60  test    eax, eax
0x18001cb62  jns     short loc_18001CB7A
0x18001cb64  mov     dword ptr [rsp+80h+var_60], eax
0x18001cb68  lea     r9, aFailedToConver_12; "Failed to convert dos path to nt path ["...
0x18001cb6f  mov     r8d, 8C6h
0x18001cb75  jmp     loc_18001CFB0
0x18001cb7a  lea     rcx, [rbp+UnicodeString]
0x18001cb7e  call    AslPathCleanUstr
0x18001cb83  mov     ebx, eax
0x18001cb85  test    eax, eax
0x18001cb87  jns     short loc_18001CB9F
0x18001cb89  mov     dword ptr [rsp+80h+var_60], eax
0x18001cb8d  lea     r9, aAslpathcleanus; "AslPathCleanUstr failed [%x]"
0x18001cb94  mov     r8d, 8D1h
0x18001cb9a  jmp     loc_18001CFB0
0x18001cb9f  movzx   eax, [rbp+UnicodeString.Length]
0x18001cba3  add     ax, 4
0x18001cba7  cmp     ax, [rbp+UnicodeString.Length]
0x18001cbab  jb      loc_18001CF9A
0x18001cbb1  mov     rcx, gs:60h
0x18001cbba  mov     edx, 8; Flags
0x18001cbbf  movzx   edi, ax
0x18001cbc2  mov     r8d, edi; Size
0x18001cbc5  mov     rcx, [rcx+30h]; HeapHandle
0x18001cbc9  call    cs:__imp_RtlAllocateHeap
0x18001cbcf  xor     r9d, r9d
0x18001cbd2  mov     r15, rax
0x18001cbd5  test    rax, rax
0x18001cbd8  jnz     short loc_18001CBE4
0x18001cbda  mov     ebx, 0C0000017h
0x18001cbdf  jmp     loc_18001CFC1
0x18001cbe4  shr     rdi, 1
0x18001cbe7  mov     esi, 1
0x18001cbec  jz      loc_18001CF8A
0x18001cbf2  movzx   eax, [rbp+UnicodeString.Length]
0x18001cbf6  mov     rdx, r15
0x18001cbf9  mov     rcx, [rbp+UnicodeString.Buffer]
0x18001cbfd  shr     rax, 1
0x18001cc00  test    rax, rax
0x18001cc03  jz      short loc_18001CC23
0x18001cc05  movzx   r8d, word ptr [rcx]
0x18001cc09  test    r8w, r8w
0x18001cc0d  jz      short loc_18001CC23
0x18001cc0f  mov     [rdx], r8w
0x18001cc13  add     rcx, 2
0x18001cc17  add     rdx, 2
0x18001cc1b  sub     rax, rsi
0x18001cc1e  sub     rdi, rsi
0x18001cc21  jnz     short loc_18001CC00
0x18001cc23  mov     rax, rdi
0x18001cc26  lea     rcx, [rdx-2]
0x18001cc2a  neg     rax
0x18001cc2d  sbb     ebx, ebx
0x18001cc2f  not     ebx
0x18001cc31  and     ebx, 80000005h
0x18001cc37  test    rdi, rdi
0x18001cc3a  cmovnz  rcx, rdx
0x18001cc3e  mov     [rcx], r9w
0x18001cc42  jz      loc_18001CF8F
0x18001cc48  mov     rcx, r15; SourceString
0x18001cc4b  call    AslpPathWildcardMakeLeaves
0x18001cc50  xor     ebx, ebx
0x18001cc52  test    eax, eax
0x18001cc54  jnz     short loc_18001CC7B
0x18001cc56  lea     r9, aFailedToSplitT; "Failed to split the wildcard path"
0x18001cc5d  mov     r8d, 8F5h
0x18001cc63  lea     rdx, aAslpathwildcar_1; "AslPathWildcardFindFirst"
0x18001cc6a  mov     ecx, esi
0x18001cc6c  mov     ebx, 0C0000039h
0x18001cc71  call    AslLogCallPrintf
0x18001cc76  jmp     loc_18001CFC1
0x18001cc7b  cmp     eax, esi
0x18001cc7d  jnz     short loc_18001CCD2
0x18001cc7f  mov     rcx, [rbp+UnicodeString.Buffer]; FileName
0x18001cc83  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x18001cc8b  call    AslDoesFileExistNtPath
0x18001cc90  test    eax, eax
0x18001cc92  jnz     short loc_18001CC9E
0x18001cc94  mov     ebx, 80000006h
0x18001cc99  jmp     loc_18001CFC1
0x18001cc9e  mov     r8, r14
0x18001cca1  mov     edx, 104h
0x18001cca6  mov     rcx, r13
0x18001cca9  call    RtlStringCchCopyW
0x18001ccae  mov     ebx, eax
0x18001ccb0  xor     eax, eax
0x18001ccb2  test    ebx, ebx
0x18001ccb4  jns     loc_18001CF64
0x18001ccba  mov     r8d, 907h
0x18001ccc0  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x18001ccc7  mov     dword ptr [rsp+80h+var_60], ebx
0x18001cccb  mov     ecx, esi
0x18001cccd  jmp     loc_18001CFB5
0x18001ccd2  mov     rcx, gs:60h
0x18001ccdb  mov     edx, 8; Flags
0x18001cce0  mov     rcx, [rcx+30h]; HeapHandle
0x18001cce4  lea     r8d, [rdx+38h]; Size
0x18001cce8  call    cs:__imp_RtlAllocateHeap
0x18001ccee  mov     [rbp+arg_8], rax
0x18001ccf2  mov     rdi, rax
0x18001ccf5  test    rax, rax
0x18001ccf8  jz      loc_18001CBDA
0x18001ccfe  mov     r8d, 4; MaxCount
0x18001cd04  lea     rdx, asc_18022BDA0; "\\??\\"
0x18001cd0b  mov     rcx, r14; String1
0x18001cd0e  call    wcsncmp_0
0x18001cd13  xorps   xmm0, xmm0
0x18001cd16  mov     ecx, ebx
0x18001cd18  test    eax, eax
0x18001cd1a  setnz   cl
0x18001cd1d  mov     [rdi], ecx
0x18001cd1f  mov     [rdi+8], r15
0x18001cd23  mov     r15, rbx
0x18001cd26  movups  xmmword ptr [rdi+10h], xmm0
0x18001cd2a  movups  xmmword ptr [rdi+20h], xmm0
0x18001cd2e  movups  xmmword ptr [rdi+30h], xmm0
0x18001cd32  call    cs:__imp_GetProcessHeap
0x18001cd38  mov     r13d, 10h
0x18001cd3e  mov     [rdi+20h], rbx
0x18001cd42  mov     r9, rax
0x18001cd45  mov     [rdi+10h], rax
0x18001cd49  mov     [rdi+30h], r13
0x18001cd4d  mov     ecx, 8000000Bh
0x18001cd52  mov     [rdi+28h], rbx
0x18001cd56  lea     r8d, [r13+10h]
0x18001cd5a  mov     [rdi+38h], rbx
0x18001cd5e  mov     eax, r8d
0x18001cd61  mov     [rdi+18h], r8
0x18001cd65  mul     rbx
0x18001cd68  mov     [rbp+Size], rbx
0x18001cd6c  test    rdx, rdx
0x18001cd6f  jnz     loc_18001CE06
0x18001cd75  mov     eax, r8d
0x18001cd78  mov     [rbp+Size], rbx
0x18001cd7c  mul     r13
0x18001cd7f  mov     r14, rax
0x18001cd82  test    rdx, rdx
0x18001cd85  jnz     short loc_18001CE06
0x18001cd87  mov     r8, rax; dwBytes
0x18001cd8a  mov     rcx, r9; hHeap
0x18001cd8d  call    cs:__imp_HeapAlloc
0x18001cd93  mov     rbx, rax
0x18001cd96  test    rax, rax
0x18001cd99  jz      short loc_18001CDFF
0x18001cd9b  mov     r8, r14; Size
0x18001cd9e  xor     edx, edx; Val
0x18001cda0  mov     rcx, rax; void *
0x18001cda3  call    memset_0
0x18001cda8  xor     r14d, r14d
0x18001cdab  mov     [rdi+38h], rbx
0x18001cdaf  mov     [rdi+28h], r13
0x18001cdb3  mov     rdx, [rdi+8]; SourceString
0x18001cdb7  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001cdbb  call    cs:__imp_RtlInitUnicodeString
0x18001cdc1  mov     r8, [rdi+8]
0x18001cdc5  lea     rdx, [rbp+DestinationString]
0x18001cdc9  mov     r9d, esi
0x18001cdcc  mov     [rsp+80h+var_58], r14w
0x18001cdd2  lea     rcx, [rbp+var_28]
0x18001cdd6  mov     [rsp+80h+var_60], r14
0x18001cddb  call    AslpPathWildcardAllocMatchNode
0x18001cde0  xor     r9d, r9d
0x18001cde3  mov     ebx, eax
0x18001cde5  test    eax, eax
0x18001cde7  jns     short loc_18001CE64
0x18001cde9  mov     dword ptr [rsp+80h+var_60], eax
0x18001cded  lea     r9, aAslppathwildca_0; "AslpPathWildcardAllocMatchNode failed t"...
0x18001cdf4  mov     r8d, 93Ah
0x18001cdfa  jmp     loc_18001CCCB
0x18001cdff  mov     ebx, 8007000Eh
0x18001ce04  jmp     short loc_18001CE08
0x18001ce06  mov     ebx, ecx
0x18001ce08  mov     r8, [rdi+38h]; lpMem
0x18001ce0c  xor     r14d, r14d
0x18001ce0f  test    r8, r8
0x18001ce12  jz      short loc_18001CE20
0x18001ce14  mov     rcx, [rdi+10h]; hHeap
0x18001ce18  xor     edx, edx; dwFlags
0x18001ce1a  call    cs:__imp_HeapFree
0x18001ce20  xorps   xmm0, xmm0
0x18001ce23  movups  xmmword ptr [rdi+10h], xmm0
0x18001ce27  movups  xmmword ptr [rdi+20h], xmm0
0x18001ce2b  movups  xmmword ptr [rdi+30h], xmm0
0x18001ce2f  test    ebx, ebx
0x18001ce31  jns     short loc_18001CDB3
0x18001ce33  lea     r9, aRtlarrayinitia; "RtlArrayInitialize failed [%x]"
0x18001ce3a  mov     dword ptr [rsp+80h+var_60], ebx
0x18001ce3e  mov     r8d, 864h
0x18001ce44  lea     rdx, aAslppathwildca_6; "AslpPathWildcardInitStack"
0x18001ce4b  mov     ecx, esi
0x18001ce4d  call    AslLogCallPrintf
0x18001ce52  lea     r9, aAslppathwildca_2; "AslpPathWildcardInitStack failed [%x]"
0x18001ce59  mov     r8d, 92Dh
0x18001ce5f  jmp     loc_18001CCC7
0x18001ce64  mov     r13, [rdi+20h]
0x18001ce68  cmp     r13, [rdi+28h]
0x18001ce6c  jb      loc_18001CF1B
0x18001ce72  lea     rcx, [r13+1]
0x18001ce76  cmp     rcx, [rdi+28h]
0x18001ce7a  ja      short loc_18001CE86
0x18001ce7c  mov     ebx, 80070057h
0x18001ce81  jmp     loc_18001CF6D
0x18001ce86  mov     rbx, [rdi+30h]
0x18001ce8a  dec     rbx
0x18001ce8d  lea     r8, [rbx+rcx]
0x18001ce91  cmp     r8, rcx
0x18001ce94  jb      loc_18001CF68
0x18001ce9a  mov     rax, [rdi+18h]
0x18001ce9e  mul     qword ptr [rdi+28h]
0x18001cea2  mov     [rbp+Size], r9
0x18001cea6  test    rdx, rdx
0x18001cea9  jnz     loc_18001CF68
0x18001ceaf  mov     rax, [rdi+18h]
0x18001ceb3  not     rbx
0x18001ceb6  and     rbx, r8
0x18001ceb9  mov     [rbp+Size], r9
0x18001cebd  mul     rbx
0x18001cec0  mov     [rbp+Size], rax
0x18001cec4  test    rdx, rdx
0x18001cec7  jnz     loc_18001CF68
0x18001cecd  mov     r8, [rdi+38h]; lpMem
0x18001ced1  mov     rcx, [rdi+10h]; hHeap
0x18001ced5  test    r8, r8
0x18001ced8  jnz     short loc_18001CEFB
0x18001ceda  mov     r8, rax; dwBytes
0x18001cedd  call    cs:__imp_HeapAlloc
0x18001cee3  mov     r14, rax
0x18001cee6  test    rax, rax
0x18001cee9  jz      short loc_18001CF07
0x18001ceeb  mov     r8, [rbp+Size]; Size
0x18001ceef  xor     edx, edx; Val
0x18001cef1  mov     rcx, rax; void *
0x18001cef4  call    memset_0
0x18001cef9  jmp     short loc_18001CF07
0x18001cefb  mov     r9, rax; dwBytes
0x18001cefe  call    cs:__imp_HeapReAlloc
0x18001cf04  mov     r14, rax
0x18001cf07  test    r14, r14
0x18001cf0a  jnz     short loc_18001CF13
0x18001cf0c  mov     ebx, 8007000Eh
0x18001cf11  jmp     short loc_18001CF6D
0x18001cf13  mov     [rdi+38h], r14
0x18001cf17  mov     [rdi+28h], rbx
0x18001cf1b  mov     rax, r13
0x18001cf1e  mul     qword ptr [rdi+18h]
0x18001cf22  test    rdx, rdx
0x18001cf25  jnz     short loc_18001CF73
0x18001cf27  add     rax, [rdi+38h]
0x18001cf2b  cmp     rax, [rdi+38h]
0x18001cf2f  jb      short loc_18001CF73
0x18001cf31  movups  xmm0, [rbp+var_28]
0x18001cf35  movups  xmmword ptr [rax], xmm0
0x18001cf38  movups  xmm1, [rbp+var_18]
0x18001cf3c  movups  xmmword ptr [rax+10h], xmm1
0x18001cf40  add     [rdi+20h], rsi
0x18001cf44  mov     rcx, [rbp+arg_0]
  ... truncated ...
```
