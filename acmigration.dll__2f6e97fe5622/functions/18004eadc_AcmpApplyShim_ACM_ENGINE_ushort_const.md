# AcmpApplyShim(_ACM_ENGINE *,ushort const *)

- ea: `0x18004eadc`
- end: `0x18004f017`
- name: `?AcmpApplyShim@@YAJPEAU_ACM_ENGINE@@PEBG@Z`
- size: `1339`
- prototype: `__int64 __fastcall(struct _ACM_ENGINE *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18004d1e0`

## callees

- `0x180001cf0`
- `0x180002790`
- `0x180002874`
- `0x18000a654`
- `0x18004eadc`
- `0x1800543c0`
- `0x180065144`
- `0x18006a010`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x18004ebf1`
- `KERNEL32!GetFileSizeEx` at `0x18004ebf1`
- `KERNEL32!ReadFile` at `0x18004eca9`
- `KERNEL32!ReadFile` at `0x18004eca9`
- `KERNEL32!CreateFileW` at `0x18004ebcd`
- `KERNEL32!CreateFileW` at `0x18004ebcd`
- `KERNEL32!GetProcessHeap` at `0x18004eb2b`
- `KERNEL32!GetProcessHeap` at `0x18004eb2b`
- `KERNEL32!HeapAlloc` at `0x18004ec25`
- `KERNEL32!HeapAlloc` at `0x18004ec25`
- `KERNEL32!CloseHandle` at `0x18004ecdb`
- `KERNEL32!CloseHandle` at `0x18004ecdb`
- `KERNEL32!GetLastError` at `0x18004ebdc`
- `KERNEL32!GetLastError` at `0x18004ebdc`
- `KERNEL32!HeapFree` at `0x18004efe6`
- `KERNEL32!HeapFree` at `0x18004efe6`

## string_xrefs

- `0x18004eb76`: `Failed to make state file path [%x]`

## pseudocode

```c
__int64 __fastcall AcmpApplyShim(struct _ACM_ENGINE *a1, const unsigned __int16 *a2)
{
  struct _ACM_ENGINE *v3; // r15
  HANDLE ProcessHeap; // rsi
  char *v5; // r13
  HRESULT v6; // eax
  signed int LastError; // ebx
  unsigned __int64 v8; // rsi
  HANDLE FileW; // rax
  void *v10; // r12
  unsigned __int64 QuadPart; // rcx
  union _LARGE_INTEGER v12; // r14
  SIZE_T v13; // rbx
  char *v14; // rax
  char *v15; // r15
  int v16; // eax
  char *v17; // rbx
  DWORD v18; // r8d
  const char *v19; // r9
  __int64 v20; // r8
  DWORD v21; // r11d
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rax
  char v24; // r10
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // r9
  unsigned __int64 v27; // rax
  __int64 v28; // rcx
  unsigned __int64 v29; // rdx
  char v30; // r9
  unsigned __int64 v31; // r8
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // r10
  const wchar_t *v34; // r14
  unsigned __int64 v35; // rdx
  char v36; // r10
  unsigned __int64 v37; // r8
  unsigned __int64 v38; // rax
  unsigned __int64 v39; // r9
  const wchar_t *v40; // rsi
  unsigned __int64 v41; // r15
  __int64 v42; // r12
  __int64 v43; // rbx
  const wchar_t **v44; // rcx
  __int64 v45; // r8
  __int64 (__fastcall *v46)(const unsigned __int16 *, const wchar_t *, _QWORD); // rax
  int v47; // ecx
  const wchar_t *v48; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-2C8h]
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-2A8h] BYREF
  DWORD NumberOfBytesRead[2]; // [rsp+48h] [rbp-2A0h] BYREF
  int v53; // [rsp+50h] [rbp-298h]
  struct _ACM_ENGINE *v54; // [rsp+58h] [rbp-290h]
  HANDLE hHeap; // [rsp+60h] [rbp-288h]
  char *v56; // [rsp+88h] [rbp-260h]
  const unsigned __int16 *v57; // [rsp+90h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+A0h] [rbp-248h] BYREF

  v57 = a2;
  v3 = a1;
  v54 = a1;
  memset_0(pszDest, 0, 0x208u);
  ProcessHeap = GetProcessHeap();
  hHeap = ProcessHeap;
  v5 = 0;
  v56 = 0;
  v6 = StringCchPrintfW(pszDest, 0x104u, L"%s\\%s", a2, L"State");
  LastError = v6;
  if ( v6 < 0 )
  {
    AslLogCallPrintf(1, "AcmpApplyShim", 800, "Failed to make state file path [%x]", v6);
    goto LABEL_106;
  }
  FileSize.QuadPart = 0;
  NumberOfBytesRead[0] = 0;
  v8 = 0;
  FileW = CreateFileW(pszDest, 0x80000000, 1u, 0, 3u, 0x8000080u, 0);
  v10 = FileW;
  if ( FileW == (HANDLE)-1LL || !GetFileSizeEx(FileW, &FileSize) )
    goto LABEL_4;
  QuadPart = FileSize.QuadPart;
  v12 = FileSize;
  if ( !FileSize.QuadPart )
  {
LABEL_13:
    v8 = v12.QuadPart;
    v16 = 0;
    goto LABEL_14;
  }
  if ( (unsigned __int64)(FileSize.QuadPart + 4095) >= FileSize.QuadPart )
  {
    v13 = (FileSize.QuadPart + 4095) & 0xFFFFFFFFFFFFF000uLL;
    v14 = (char *)HeapAlloc(hHeap, 0, v13);
    v15 = v14;
    if ( v14 )
      memset_0(v14, 0, v13);
    QuadPart = FileSize.QuadPart;
    if ( !v15 )
    {
      v16 = -2147024882;
      v3 = v54;
      goto LABEL_14;
    }
    v5 = v15;
    v56 = v15;
    v3 = v54;
    goto LABEL_13;
  }
  v16 = -2147483637;
LABEL_14:
  if ( v16 )
  {
    LastError = 14;
    goto LABEL_23;
  }
  v17 = v5;
  if ( QuadPart )
  {
    while ( 1 )
    {
      v18 = -1;
      if ( QuadPart < 0xFFFFFFFF )
        v18 = QuadPart;
      if ( !ReadFile(v10, v17, v18, NumberOfBytesRead, 0) )
        break;
      QuadPart = FileSize.QuadPart - NumberOfBytesRead[0];
      FileSize.QuadPart = QuadPart;
      v17 += NumberOfBytesRead[0];
      if ( !QuadPart )
        goto LABEL_22;
    }
LABEL_4:
    LastError = GetLastError();
    goto LABEL_23;
  }
LABEL_22:
  LastError = 0;
LABEL_23:
  if ( v10 != (void *)-1LL )
    CloseHandle(v10);
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( (unsigned int)(LastError + 2147024894) <= 1 )
    goto LABEL_104;
  if ( LastError >= 0 )
  {
    v21 = 0;
    NumberOfBytesRead[0] = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    while ( v22 <= v8 )
    {
      v25 = v22 + 8;
      if ( v22 + 8 < v22 )
        break;
      if ( v25 > v8 )
        break;
      v23 = *(_QWORD *)&v5[v22];
      v22 += 8LL;
      v26 = v25 + HIDWORD(v23);
      if ( v26 < v25 || v26 + 3 < v26 || ((v26 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v8 )
        break;
      if ( (_DWORD)v23 == 3 )
      {
        v24 = 1;
        break;
      }
      v22 = (v26 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
    }
    if ( v24 )
      v27 = HIDWORD(v23);
    else
      LODWORD(v27) = 0;
    if ( !v24 )
    {
      LastError = -2147024894;
LABEL_58:
      v19 = "Failed to find NoApply parameter [%x]";
      v20 = 827;
      goto LABEL_30;
    }
    v28 = 4;
    if ( (unsigned int)v27 > 4 )
    {
      LastError = -2147483637;
      goto LABEL_58;
    }
    if ( (unsigned int)v27 < 4 )
      v28 = (unsigned int)v27;
    if ( (_DWORD)v28 )
    {
      if ( v22 > v8 || v28 + v22 < v22 || v28 + v22 > v8 )
      {
        LastError = -2147024809;
      }
      else
      {
        memcpy_0(NumberOfBytesRead, &v5[v22], (unsigned int)v28);
        LastError = 0;
        v21 = NumberOfBytesRead[0];
      }
    }
    else
    {
      LastError = 0;
    }
    if ( LastError < 0 )
      goto LABEL_58;
    if ( v21 != 1 )
    {
      v29 = 0;
      v30 = 0;
      while ( v29 <= v8 )
      {
        v31 = v29 + 8;
        if ( v29 + 8 < v29 )
          break;
        if ( v31 > v8 )
          break;
        v32 = *(_QWORD *)&v5[v29];
        v29 += 8LL;
        v33 = v31 + HIDWORD(v32);
        if ( v33 < v31 || v33 + 3 < v33 || ((v33 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v8 )
          break;
        if ( (_DWORD)v32 == 1 )
        {
          v30 = 1;
          break;
        }
        v29 = (v33 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
      }
      if ( v30 )
        v34 = (const wchar_t *)&v5[v29];
      else
        v34 = 0;
      FileSize.QuadPart = (LONGLONG)v34;
      if ( !v30 )
      {
        LastError = -2147023728;
        v19 = "Failed to find Name parameter [%x]";
        v20 = 847;
        goto LABEL_30;
      }
      v35 = 0;
      v36 = 0;
      while ( v35 <= v8 )
      {
        v37 = v35 + 8;
        if ( v35 + 8 < v35 )
          break;
        if ( v37 > v8 )
          break;
        v38 = *(_QWORD *)&v5[v35];
        v35 += 8LL;
        v39 = v37 + HIDWORD(v38);
        if ( v39 < v37 || v39 + 3 < v39 || ((v39 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v8 )
          break;
        if ( (_DWORD)v38 == 2 )
        {
          v36 = 1;
          break;
        }
        v35 = (v39 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
      }
      if ( v36 )
        v40 = (const wchar_t *)&v5[v35];
      else
        v40 = 0;
      *(_QWORD *)NumberOfBytesRead = v40;
      if ( v34 && (v41 = *((_QWORD *)v3 + 66)) != 0 && (v42 = *((_QWORD *)v54 + 65)) != 0 )
      {
        v43 = 0;
        while ( 1 )
        {
          v44 = *(const wchar_t ***)(v42 + 8 * v43);
          if ( v44 )
          {
            if ( !wcsicmp(*v44, v34) )
              break;
          }
          if ( ++v43 >= v41 )
            goto LABEL_95;
        }
        v45 = *(_QWORD *)(v42 + 8 * v43);
      }
      else
      {
LABEL_95:
        v45 = 0;
      }
      if ( !v45 )
      {
        LastError = -2147023728;
        AslLogCallPrintf(1, "AcmpApplyShim", 864, "Failed to find shim [%S]", v34);
        goto LABEL_105;
      }
      v46 = *(__int64 (__fastcall **)(const unsigned __int16 *, const wchar_t *, _QWORD))(v45 + 24);
      if ( v46 )
      {
        v47 = v46(v57, v40, *(_QWORD *)(v45 + 48));
        v53 = v47;
        if ( v47 < 0 )
        {
          v48 = L"null";
          if ( v40 )
            v48 = v40;
          AslLogCallPrintf(2, "AcmpApplyShim", 897, "Apply failed for shim [%S (%S)] [%x]", v34, v48, v47);
        }
      }
    }
LABEL_104:
    LastError = 0;
    goto LABEL_105;
  }
  v19 = "Failed to load state [%x]";
  v20 = 821;
LABEL_30:
  dwCreationDisposition[0] = LastError;
  AslLogCallPrintf(1, "AcmpApplyShim", v20, v19, *(_QWORD *)dwCreationDisposition);
LABEL_105:
  ProcessHeap = hHeap;
LABEL_106:
  if ( v5 )
    HeapFree(ProcessHeap, 0, v5);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18004eadc  mov     [rsp+arg_10], rbx
0x18004eae1  push    rsi
0x18004eae2  push    r12
0x18004eae4  push    r13
0x18004eae6  push    r14
0x18004eae8  push    r15
0x18004eaea  sub     rsp, 2C0h
0x18004eaf1  mov     rax, cs:__security_cookie
0x18004eaf8  xor     rax, rsp
0x18004eafb  mov     [rsp+2E8h+var_38], rax
0x18004eb03  mov     rbx, rdx
0x18004eb06  mov     [rsp+2E8h+var_258], rdx
0x18004eb0e  mov     r15, rcx
0x18004eb11  mov     [rsp+2E8h+var_290], rcx
0x18004eb16  xor     edx, edx; Val
0x18004eb18  mov     r8d, 208h; Size
0x18004eb1e  lea     rcx, [rsp+2E8h+pszDest]; void *
0x18004eb26  call    memset_0
0x18004eb2b  call    cs:__imp_GetProcessHeap
0x18004eb31  mov     rsi, rax
0x18004eb34  mov     [rsp+2E8h+hHeap], rax
0x18004eb39  xor     r13d, r13d
0x18004eb3c  mov     [rsp+2E8h+var_260], r13
0x18004eb44  lea     rax, aState; "State"
0x18004eb4b  mov     qword ptr [rsp+2E8h+dwCreationDisposition], rax
0x18004eb50  mov     r9, rbx
0x18004eb53  lea     r8, aSS_0; "%s\\%s"
0x18004eb5a  mov     edx, 104h; cchDest
0x18004eb5f  lea     rcx, [rsp+2E8h+pszDest]; pszDest
0x18004eb67  call    StringCchPrintfW
0x18004eb6c  mov     ebx, eax
0x18004eb6e  test    eax, eax
0x18004eb70  jns     short loc_18004EB98
0x18004eb72  mov     [rsp+2E8h+dwCreationDisposition], eax
0x18004eb76  lea     r9, aFailedToMakeSt; "Failed to make state file path [%x]"
0x18004eb7d  mov     r8d, 320h
0x18004eb83  lea     rdx, aAcmpapplyshim; "AcmpApplyShim"
0x18004eb8a  lea     ecx, [r13+1]
0x18004eb8e  call    AslLogCallPrintf
0x18004eb93  jmp     loc_18004EFD9
0x18004eb98  mov     qword ptr [rsp+2E8h+FileSize], r13
0x18004eb9d  mov     [rsp+2E8h+NumberOfBytesRead], r13d
0x18004eba2  xor     esi, esi
0x18004eba4  mov     [rsp+2E8h+hTemplateFile], rsi; hTemplateFile
0x18004eba9  mov     [rsp+2E8h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x18004ebb1  mov     [rsp+2E8h+dwCreationDisposition], 3; dwCreationDisposition
0x18004ebb9  xor     r9d, r9d; lpSecurityAttributes
0x18004ebbc  mov     edx, 80000000h; dwDesiredAccess
0x18004ebc1  lea     r8d, [rsi+1]; dwShareMode
0x18004ebc5  lea     rcx, [rsp+2E8h+pszDest]; lpFileName
0x18004ebcd  call    cs:__imp_CreateFileW
0x18004ebd3  mov     r12, rax
0x18004ebd6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004ebda  jnz     short loc_18004EBE9
0x18004ebdc  call    cs:__imp_GetLastError
0x18004ebe2  mov     ebx, eax
0x18004ebe4  jmp     loc_18004ECD2
0x18004ebe9  lea     rdx, [rsp+2E8h+FileSize]; lpFileSize
0x18004ebee  mov     rcx, r12; hFile
0x18004ebf1  call    cs:__imp_GetFileSizeEx
0x18004ebf7  test    eax, eax
0x18004ebf9  jz      short loc_18004EBDC
0x18004ebfb  mov     rcx, qword ptr [rsp+2E8h+FileSize]
0x18004ec00  mov     r14, rcx
0x18004ec03  test    rcx, rcx
0x18004ec06  jz      short loc_18004EC66
0x18004ec08  lea     rbx, [rcx+0FFFh]
0x18004ec0f  cmp     rbx, rcx
0x18004ec12  jb      short loc_18004EC76
0x18004ec14  and     rbx, 0FFFFFFFFFFFFF000h
0x18004ec1b  mov     r8, rbx; dwBytes
0x18004ec1e  xor     edx, edx; dwFlags
0x18004ec20  mov     rcx, [rsp+2E8h+hHeap]; hHeap
0x18004ec25  call    cs:__imp_HeapAlloc
0x18004ec2b  mov     r15, rax
0x18004ec2e  test    rax, rax
0x18004ec31  jz      short loc_18004EC40
0x18004ec33  mov     r8, rbx; Size
0x18004ec36  xor     edx, edx; Val
0x18004ec38  mov     rcx, rax; void *
0x18004ec3b  call    memset_0
0x18004ec40  mov     rcx, qword ptr [rsp+2E8h+FileSize]
0x18004ec45  test    r15, r15
0x18004ec48  jnz     short loc_18004EC56
0x18004ec4a  mov     eax, 8007000Eh
0x18004ec4f  mov     r15, [rsp+2E8h+var_290]
0x18004ec54  jmp     short loc_18004EC6B
0x18004ec56  mov     r13, r15
0x18004ec59  mov     [rsp+2E8h+var_260], r15
0x18004ec61  mov     r15, [rsp+2E8h+var_290]
0x18004ec66  mov     rsi, r14
0x18004ec69  xor     eax, eax
0x18004ec6b  test    eax, eax
0x18004ec6d  jz      short loc_18004EC7D
0x18004ec6f  mov     ebx, 0Eh
0x18004ec74  jmp     short loc_18004ECD2
0x18004ec76  mov     eax, 8000000Bh
0x18004ec7b  jmp     short loc_18004EC6B
0x18004ec7d  mov     rbx, r13
0x18004ec80  test    rcx, rcx
0x18004ec83  jz      short loc_18004ECD0
0x18004ec85  mov     r14d, 0FFFFFFFFh
0x18004ec8b  mov     r8d, r14d
0x18004ec8e  cmp     rcx, r14
0x18004ec91  cmovb   r8d, ecx; nNumberOfBytesToRead
0x18004ec95  mov     qword ptr [rsp+2E8h+dwCreationDisposition], 0; lpOverlapped
0x18004ec9e  lea     r9, [rsp+2E8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004eca3  mov     rdx, rbx; lpBuffer
0x18004eca6  mov     rcx, r12; hFile
0x18004eca9  call    cs:__imp_ReadFile
0x18004ecaf  test    eax, eax
0x18004ecb1  jz      loc_18004EBDC
0x18004ecb7  mov     eax, [rsp+2E8h+NumberOfBytesRead]
0x18004ecbb  mov     rcx, qword ptr [rsp+2E8h+FileSize]
0x18004ecc0  sub     rcx, rax
0x18004ecc3  mov     qword ptr [rsp+2E8h+FileSize], rcx
0x18004ecc8  add     rbx, rax
0x18004eccb  test    rcx, rcx
0x18004ecce  jnz     short loc_18004EC8B
0x18004ecd0  xor     ebx, ebx
0x18004ecd2  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18004ecd6  jz      short loc_18004ECE1
0x18004ecd8  mov     rcx, r12; hObject
0x18004ecdb  call    cs:__imp_CloseHandle
0x18004ece1  test    ebx, ebx
0x18004ece3  jle     short loc_18004ECEE
0x18004ece5  movzx   ebx, bx
0x18004ece8  or      ebx, 80070000h
0x18004ecee  lea     eax, [rbx+7FF8FFFEh]
0x18004ecf4  cmp     eax, 1
0x18004ecf7  jbe     loc_18004EFD2
0x18004ecfd  test    ebx, ebx
0x18004ecff  jns     short loc_18004ED28
0x18004ed01  lea     r9, aFailedToLoadSt; "Failed to load state [%x]"
0x18004ed08  mov     r8d, 335h
0x18004ed0e  mov     [rsp+2E8h+dwCreationDisposition], ebx
0x18004ed12  lea     rdx, aAcmpapplyshim; "AcmpApplyShim"
0x18004ed19  mov     ecx, 1
0x18004ed1e  call    AslLogCallPrintf
0x18004ed23  jmp     loc_18004EFD4
0x18004ed28  xor     r11d, r11d
0x18004ed2b  mov     [rsp+2E8h+NumberOfBytesRead], r11d
0x18004ed30  xor     edx, edx
0x18004ed32  xor     eax, eax
0x18004ed34  xor     r10b, r10b
0x18004ed37  cmp     rdx, rsi
0x18004ed3a  ja      short loc_18004ED7F
0x18004ed3c  lea     r8, [rdx+8]
0x18004ed40  cmp     r8, rdx
0x18004ed43  jb      short loc_18004ED7F
0x18004ed45  cmp     r8, rsi
0x18004ed48  ja      short loc_18004ED7F
0x18004ed4a  mov     rax, [rdx+r13]
0x18004ed4e  mov     rdx, r8
0x18004ed51  mov     r9, rax
0x18004ed54  shr     r9, 20h
0x18004ed58  add     r9, r8
0x18004ed5b  cmp     r9, r8
0x18004ed5e  jb      short loc_18004ED7F
0x18004ed60  lea     rcx, [r9+3]
0x18004ed64  cmp     rcx, r9
0x18004ed67  jb      short loc_18004ED7F
0x18004ed69  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18004ed6d  cmp     rcx, rsi
0x18004ed70  ja      short loc_18004ED7F
0x18004ed72  cmp     eax, 3
0x18004ed75  jz      short loc_18004ED7C
0x18004ed77  mov     rdx, rcx
0x18004ed7a  jmp     short loc_18004ED37
0x18004ed7c  mov     r10b, 1
0x18004ed7f  test    r10b, r10b
0x18004ed82  jz      short loc_18004ED8A
0x18004ed84  shr     rax, 20h
0x18004ed88  jmp     short loc_18004ED8C
0x18004ed8a  xor     eax, eax
0x18004ed8c  test    r10b, r10b
0x18004ed8f  jnz     short loc_18004ED98
0x18004ed91  mov     ebx, 80070002h
0x18004ed96  jmp     short loc_18004EDE8
0x18004ed98  mov     ecx, 4
0x18004ed9d  cmp     eax, ecx
0x18004ed9f  jbe     short loc_18004EDA8
0x18004eda1  mov     ebx, 8000000Bh
0x18004eda6  jmp     short loc_18004EDE8
0x18004eda8  cmovb   ecx, eax
0x18004edab  test    ecx, ecx
0x18004edad  jnz     short loc_18004EDB3
0x18004edaf  xor     ebx, ebx
0x18004edb1  jmp     short loc_18004EDE4
0x18004edb3  cmp     rdx, rsi
0x18004edb6  ja      short loc_18004EDDF
0x18004edb8  mov     r8d, ecx; Size
0x18004edbb  lea     rax, [rcx+rdx]
0x18004edbf  cmp     rax, rdx
0x18004edc2  jb      short loc_18004EDDF
0x18004edc4  cmp     rax, rsi
0x18004edc7  ja      short loc_18004EDDF
0x18004edc9  add     rdx, r13; Src
0x18004edcc  lea     rcx, [rsp+2E8h+NumberOfBytesRead]; void *
0x18004edd1  call    memcpy_0
0x18004edd6  xor     ebx, ebx
0x18004edd8  mov     r11d, [rsp+2E8h+NumberOfBytesRead]
0x18004eddd  jmp     short loc_18004EDE4
0x18004eddf  mov     ebx, 80070057h
0x18004ede4  test    ebx, ebx
0x18004ede6  jns     short loc_18004EDFA
0x18004ede8  lea     r9, aFailedToFindNo; "Failed to find NoApply parameter [%x]"
0x18004edef  mov     r8d, 33Bh
0x18004edf5  jmp     loc_18004ED0E
0x18004edfa  cmp     r11d, 1
0x18004edfe  jz      loc_18004EFD2
0x18004ee04  xor     edx, edx
0x18004ee06  xor     r9b, r9b
0x18004ee09  cmp     rdx, rsi
0x18004ee0c  ja      short loc_18004EE51
0x18004ee0e  lea     r8, [rdx+8]
0x18004ee12  cmp     r8, rdx
0x18004ee15  jb      short loc_18004EE51
0x18004ee17  cmp     r8, rsi
0x18004ee1a  ja      short loc_18004EE51
0x18004ee1c  mov     rax, [rdx+r13]
0x18004ee20  mov     rdx, r8
0x18004ee23  mov     r10, rax
0x18004ee26  shr     r10, 20h
0x18004ee2a  add     r10, r8
0x18004ee2d  cmp     r10, r8
0x18004ee30  jb      short loc_18004EE51
0x18004ee32  lea     rcx, [r10+3]
0x18004ee36  cmp     rcx, r10
0x18004ee39  jb      short loc_18004EE51
0x18004ee3b  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18004ee3f  cmp     rcx, rsi
0x18004ee42  ja      short loc_18004EE51
0x18004ee44  cmp     eax, 1
0x18004ee47  jz      short loc_18004EE4E
0x18004ee49  mov     rdx, rcx
0x18004ee4c  jmp     short loc_18004EE09
0x18004ee4e  mov     r9b, 1
0x18004ee51  test    r9b, r9b
0x18004ee54  jz      short loc_18004EE5C
0x18004ee56  lea     r14, [rdx+r13]
0x18004ee5a  jmp     short loc_18004EE5F
0x18004ee5c  xor     r14d, r14d
0x18004ee5f  mov     qword ptr [rsp+2E8h+FileSize], r14
0x18004ee64  test    r9b, r9b
0x18004ee67  jnz     short loc_18004EE80
0x18004ee69  mov     ebx, 80070490h
0x18004ee6e  lea     r9, aFailedToFindNa; "Failed to find Name parameter [%x]"
0x18004ee75  mov     r8d, 34Fh
0x18004ee7b  jmp     loc_18004ED0E
0x18004ee80  xor     edx, edx
0x18004ee82  xor     r10b, r10b
0x18004ee85  cmp     rdx, rsi
0x18004ee88  ja      short loc_18004EECD
0x18004ee8a  lea     r8, [rdx+8]
0x18004ee8e  cmp     r8, rdx
0x18004ee91  jb      short loc_18004EECD
0x18004ee93  cmp     r8, rsi
0x18004ee96  ja      short loc_18004EECD
0x18004ee98  mov     rax, [rdx+r13]
0x18004ee9c  mov     rdx, r8
0x18004ee9f  mov     r9, rax
0x18004eea2  shr     r9, 20h
0x18004eea6  add     r9, r8
0x18004eea9  cmp     r9, r8
0x18004eeac  jb      short loc_18004EECD
0x18004eeae  lea     rcx, [r9+3]
0x18004eeb2  cmp     rcx, r9
0x18004eeb5  jb      short loc_18004EECD
0x18004eeb7  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18004eebb  cmp     rcx, rsi
0x18004eebe  ja      short loc_18004EECD
0x18004eec0  cmp     eax, 2
0x18004eec3  jz      short loc_18004EECA
0x18004eec5  mov     rdx, rcx
0x18004eec8  jmp     short loc_18004EE85
0x18004eeca  mov     r10b, 1
0x18004eecd  test    r10b, r10b
0x18004eed0  jz      short loc_18004EED8
0x18004eed2  lea     rsi, [rdx+r13]
0x18004eed6  jmp     short loc_18004EEDA
0x18004eed8  xor     esi, esi
0x18004eeda  mov     qword ptr [rsp+2E8h+NumberOfBytesRead], rsi
0x18004eedf  test    r14, r14
0x18004eee2  jz      short loc_18004EF29
0x18004eee4  mov     r15, [r15+210h]
0x18004eeeb  test    r15, r15
0x18004eeee  jz      short loc_18004EF29
0x18004eef0  mov     r12, [rsp+2E8h+var_290]
0x18004eef5  mov     r12, [r12+208h]
0x18004eefd  test    r12, r12
0x18004ef00  jz      short loc_18004EF29
0x18004ef02  xor     ebx, ebx
0x18004ef04  test    r15, r15
0x18004ef07  jz      short loc_18004EF29
0x18004ef09  mov     rcx, [r12+rbx*8]
0x18004ef0d  test    rcx, rcx
0x18004ef10  jz      short loc_18004EF21
0x18004ef12  mov     rdx, r14; String2
0x18004ef15  mov     rcx, [rcx]; String1
  ... truncated ...
```
