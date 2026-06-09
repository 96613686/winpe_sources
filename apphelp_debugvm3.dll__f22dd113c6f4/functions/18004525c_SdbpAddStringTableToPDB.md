# SdbpAddStringTableToPDB

- ea: `0x18004525c`
- end: `0x1800455af`
- name: `SdbpAddStringTableToPDB`
- size: `851`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180044b60`

## callees

- `0x18000f114`
- `0x180018f20`
- `0x18001a900`
- `0x180037274`
- `0x18003ce10`
- `0x18003f760`
- `0x18004525c`
- `0x18004afa4`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlCreateUnicodeString` at `0x1800454fe`
- `ntdll!RtlCreateUnicodeString` at `0x1800454fe`
- `ntdll!NtQueryInformationFile` at `0x18004541b`
- `ntdll!NtQueryInformationFile` at `0x18004541b`
- `ntdll!RtlGetFileMUIPath` at `0x180045344`
- `ntdll!RtlGetFileMUIPath` at `0x1800453af`
- `ntdll!RtlGetFileMUIPath` at `0x180045344`
- `ntdll!RtlGetFileMUIPath` at `0x1800453af`
- `ntdll!RtlAllocateHeap` at `0x180045374`
- `ntdll!RtlAllocateHeap` at `0x18004548a`
- `ntdll!RtlAllocateHeap` at `0x180045374`
- `ntdll!RtlAllocateHeap` at `0x18004548a`

## string_xrefs

- `0x1800454de`: `Failed to write the header to disk`
- `0x1800452f1`: `Failed to retrieve the full path to AcRes.dll`
- `0x180045549`: `Couldn't get the .mui file path`
- `0x1800453d7`: `Error: Failed to open AcRes.dll.mui [%x]`
- `0x18004544d`: `Failed to create the string table`
- `0x180045508`: `Error copying string table temp filename`

## pseudocode

```c
__int64 __fastcall SdbpAddStringTableToPDB(__int64 a1)
{
  unsigned int v2; // r14d
  WCHAR *v3; // rbx
  NTSTATUS v4; // eax
  const char *v5; // r9
  __int64 v6; // r8
  SIZE_T v7; // rsi
  __int64 Database; // rax
  PVOID Heap; // rax
  PVOID v10; // r15
  FILE_INFORMATION_CLASS FileInformationClass[2]; // [rsp+20h] [rbp-E0h]
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v14; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-A8h] BYREF
  __int128 FileInformation; // [rsp+68h] [rbp-98h] BYREF
  __int64 v19; // [rsp+78h] [rbp-88h]
  _BYTE v20[528]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SourceString[264]; // [rsp+290h] [rbp+190h] BYREF

  v2 = 0;
  memset_0(v20, 0, 0x208u);
  memset_0(SourceString, 0, 0x208u);
  FileHandle = (HANDLE)-1LL;
  v14 = 0;
  v19 = 0;
  FileInformation = 0;
  v13 = 0;
  IoStatusBlock = 0;
  v15 = 0;
  if ( (unsigned int)SdbGetPathResourceDll(v20) )
  {
    v3 = 0;
    v13 = 0;
    if ( (int)RtlGetFileMUIPath(8, v20, 0, &v13, 0, &v14, &v15) >= 0
      && v14
      && ((v3 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * v14)) == 0
       || (v13 = 0, (int)RtlGetFileMUIPath(8, v20, 0, &v13, v3, &v14, &v15) >= 0))
      && v3 )
    {
      v4 = AslFileOpen(&FileHandle, v3);
      if ( v4 < 0 )
      {
        v5 = "Error: Failed to open AcRes.dll.mui [%x]";
        v6 = 345;
LABEL_10:
        FileInformationClass[0] = v4;
        AslLogCallPrintf(1, "SdbpAddStringTableToPDB", v6, v5, *(_QWORD *)FileInformationClass);
        goto LABEL_28;
      }
      v4 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
      if ( v4 < 0 )
      {
        v5 = "Unsuccessful. Status: 0x%x";
        v6 = 360;
        goto LABEL_10;
      }
      v7 = DWORD2(FileInformation);
      Database = SdbCreateDatabase(0);
      *(_QWORD *)(a1 + 2640) = Database;
      if ( !Database )
      {
        AslLogCallPrintf(1, "SdbpAddStringTableToPDB", 372, "Failed to create the string table");
        goto LABEL_28;
      }
      *(_QWORD *)(Database + 2640) = Database;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v7);
      v10 = Heap;
      if ( Heap )
      {
        memset_0(Heap, 0, v7);
        if ( (unsigned int)SdbpWriteBufferedData(*(_QWORD *)(a1 + 2640), 12, v10, (unsigned int)v7, 1) )
        {
          if ( RtlCreateUnicodeString((PUNICODE_STRING)(a1 + 2672), SourceString) )
          {
            if ( !*(_QWORD *)(a1 + 2648) )
            {
              v4 = AslHashCreate();
              if ( v4 < 0 )
              {
                v5 = "Error creating hash table [%x]";
                v6 = 420;
                goto LABEL_10;
              }
            }
            v2 = 1;
          }
          else
          {
            AslLogCallPrintf(1, "SdbpAddStringTableToPDB", 411, "Error copying string table temp filename");
          }
        }
        else
        {
          AslLogCallPrintf(1, "SdbpAddStringTableToPDB", 403, "Failed to write the header to disk");
        }
      }
      else
      {
        FileInformationClass[0] = v7;
        AslLogCallPrintf(
          1,
          "SdbpAddStringTableToPDB",
          389,
          "Failed to allocate '%ld' bytes for help center URL",
          *(_QWORD *)FileInformationClass);
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbpAddStringTableToPDB", 335, "Couldn't get the .mui file path");
      if ( !v3 )
        return v2;
    }
LABEL_28:
    AslFree(NtCurrentPeb()->ProcessHeap, v3);
    return v2;
  }
  AslLogCallPrintf(1, "SdbpAddStringTableToPDB", 298, "Failed to retrieve the full path to AcRes.dll");
  return v2;
}

```

## disassembly

```asm
0x18004525c  mov     [rsp-8+arg_8], rbx
0x180045261  mov     [rsp-8+arg_10], rsi
0x180045266  push    rbp
0x180045267  push    rdi
0x180045268  push    r12
0x18004526a  push    r14
0x18004526c  push    r15
0x18004526e  lea     rbp, [rsp-3B0h]
0x180045276  sub     rsp, 4B0h
0x18004527d  mov     rax, cs:__security_cookie
0x180045284  xor     rax, rsp
0x180045287  mov     [rbp+3D0h+var_30], rax
0x18004528e  mov     rdi, rcx
0x180045291  mov     ebx, 208h
0x180045296  mov     r8d, ebx; Size
0x180045299  lea     rcx, [rbp+3D0h+var_450]; void *
0x18004529d  xor     edx, edx; Val
0x18004529f  xor     r14d, r14d
0x1800452a2  call    memset_0
0x1800452a7  mov     r8d, ebx; Size
0x1800452aa  lea     rcx, [rbp+3D0h+SourceString]; void *
0x1800452b1  xor     edx, edx; Val
0x1800452b3  call    memset_0
0x1800452b8  xorps   xmm0, xmm0
0x1800452bb  mov     [rsp+4D0h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800452c4  xor     eax, eax
0x1800452c6  mov     [rsp+4D0h+var_48C], r14d
0x1800452cb  lea     rcx, [rbp+3D0h+var_450]
0x1800452cf  mov     [rsp+4D0h+var_458], rax
0x1800452d4  movups  [rsp+4D0h+FileInformation], xmm0
0x1800452d9  mov     [rsp+4D0h+var_490], r14d
0x1800452de  movups  xmmword ptr [rsp+4D0h+IoStatusBlock], xmm0
0x1800452e3  mov     [rsp+4D0h+var_488], r14
0x1800452e8  call    SdbGetPathResourceDll
0x1800452ed  test    eax, eax
0x1800452ef  jnz     short loc_180045312
0x1800452f1  lea     r9, aFailedToRetrie_4; "Failed to retrieve the full path to AcR"...
0x1800452f8  mov     r8d, 12Ah
0x1800452fe  lea     rdx, aSdbpaddstringt_0; "SdbpAddStringTableToPDB"
0x180045305  lea     ecx, [rax+1]
0x180045308  call    AslLogCallPrintf
0x18004530d  jmp     loc_180045581
0x180045312  xor     ebx, ebx
0x180045314  lea     rax, [rsp+4D0h+var_488]
0x180045319  mov     [rsp+4D0h+var_4A0], rax
0x18004531e  lea     r9, [rsp+4D0h+var_490]
0x180045323  lea     rax, [rsp+4D0h+var_48C]
0x180045328  mov     [rsp+4D0h+var_490], ebx
0x18004532c  mov     [rsp+4D0h+var_4A8], rax
0x180045331  lea     rdx, [rbp+3D0h+var_450]
0x180045335  lea     r15d, [rbx+8]
0x180045339  mov     qword ptr [rsp+4D0h+FileInformationClass], rbx
0x18004533e  mov     ecx, r15d
0x180045341  xor     r8d, r8d
0x180045344  call    cs:__imp_RtlGetFileMUIPath
0x18004534a  test    eax, eax
0x18004534c  js      loc_180045549
0x180045352  mov     eax, [rsp+4D0h+var_48C]
0x180045356  test    eax, eax
0x180045358  jz      loc_180045549
0x18004535e  mov     rcx, gs:60h
0x180045367  mov     r8d, eax
0x18004536a  add     r8, r8; Size
0x18004536d  mov     edx, r15d; Flags
0x180045370  mov     rcx, [rcx+30h]; HeapHandle
0x180045374  call    cs:__imp_RtlAllocateHeap
0x18004537a  mov     rbx, rax
0x18004537d  test    rax, rax
0x180045380  jz      short loc_1800453BD
0x180045382  lea     rax, [rsp+4D0h+var_488]
0x180045387  mov     [rsp+4D0h+var_490], r14d
0x18004538c  mov     [rsp+4D0h+var_4A0], rax
0x180045391  lea     r9, [rsp+4D0h+var_490]
0x180045396  lea     rax, [rsp+4D0h+var_48C]
0x18004539b  xor     r8d, r8d
0x18004539e  mov     [rsp+4D0h+var_4A8], rax
0x1800453a3  lea     rdx, [rbp+3D0h+var_450]
0x1800453a7  mov     ecx, r15d
0x1800453aa  mov     qword ptr [rsp+4D0h+FileInformationClass], rbx
0x1800453af  call    cs:__imp_RtlGetFileMUIPath
0x1800453b5  test    eax, eax
0x1800453b7  js      loc_180045549
0x1800453bd  test    rbx, rbx
0x1800453c0  jz      loc_180045549
0x1800453c6  mov     rdx, rbx; FileName
0x1800453c9  lea     rcx, [rsp+4D0h+FileHandle]; FileHandle
0x1800453ce  call    AslFileOpen
0x1800453d3  test    eax, eax
0x1800453d5  jns     short loc_1800453FE
0x1800453d7  lea     r9, aErrorFailedToO; "Error: Failed to open AcRes.dll.mui [%x"...
0x1800453de  mov     r8d, 159h
0x1800453e4  mov     [rsp+4D0h+FileInformationClass], eax
0x1800453e8  lea     rdx, aSdbpaddstringt_0; "SdbpAddStringTableToPDB"
0x1800453ef  mov     ecx, 1
0x1800453f4  call    AslLogCallPrintf
0x1800453f9  jmp     loc_18004556C
0x1800453fe  mov     rcx, [rsp+4D0h+FileHandle]; FileHandle
0x180045403  lea     r8, [rsp+4D0h+FileInformation]; FileInformation
0x180045408  mov     r9d, 18h; Length
0x18004540e  mov     [rsp+4D0h+FileInformationClass], 5; FileInformationClass
0x180045416  lea     rdx, [rsp+4D0h+IoStatusBlock]; IoStatusBlock
0x18004541b  call    cs:__imp_NtQueryInformationFile
0x180045421  test    eax, eax
0x180045423  jns     short loc_180045434
0x180045425  lea     r9, aUnsuccessfulSt; "Unsuccessful. Status: 0x%x"
0x18004542c  mov     r8d, 168h
0x180045432  jmp     short loc_1800453E4
0x180045434  mov     esi, dword ptr [rsp+4D0h+FileInformation+8]
0x180045438  xor     edx, edx
0x18004543a  xor     ecx, ecx; lpFileName
0x18004543c  call    SdbCreateDatabase
0x180045441  mov     [rdi+0A50h], rax
0x180045448  test    rax, rax
0x18004544b  jnz     short loc_180045470
0x18004544d  lea     r9, aFailedToCreate_8; "Failed to create the string table"
0x180045454  mov     r8d, 174h
0x18004545a  lea     rdx, aSdbpaddstringt_0; "SdbpAddStringTableToPDB"
0x180045461  mov     ecx, 1
0x180045466  call    AslLogCallPrintf
0x18004546b  jmp     loc_18004556C
0x180045470  mov     [rax+0A50h], rax
0x180045477  mov     r8, rsi; Size
0x18004547a  mov     rcx, gs:60h
0x180045483  mov     edx, r15d; Flags
0x180045486  mov     rcx, [rcx+30h]; HeapHandle
0x18004548a  call    cs:__imp_RtlAllocateHeap
0x180045490  mov     r15, rax
0x180045493  test    rax, rax
0x180045496  jnz     short loc_1800454AE
0x180045498  mov     [rsp+4D0h+FileInformationClass], esi
0x18004549c  lea     r9, aFailedToAlloca_2; "Failed to allocate '%ld' bytes for help"...
0x1800454a3  mov     r8d, 185h
0x1800454a9  jmp     loc_1800453E8
0x1800454ae  mov     r8, rsi; Size
0x1800454b1  xor     edx, edx; Val
0x1800454b3  mov     rcx, r15; void *
0x1800454b6  call    memset_0
0x1800454bb  mov     rcx, [rdi+0A50h]
0x1800454c2  mov     r9d, esi
0x1800454c5  mov     r8, r15
0x1800454c8  mov     [rsp+4D0h+FileInformationClass], 1
0x1800454d0  mov     edx, 0Ch
0x1800454d5  call    SdbpWriteBufferedData
0x1800454da  test    eax, eax
0x1800454dc  jnz     short loc_1800454F0
0x1800454de  lea     r9, aFailedToWriteT_3; "Failed to write the header to disk"
0x1800454e5  mov     r8d, 193h
0x1800454eb  jmp     loc_18004545A
0x1800454f0  lea     rcx, [rdi+0A70h]; DestinationString
0x1800454f7  lea     rdx, [rbp+3D0h+SourceString]; SourceString
0x1800454fe  call    cs:__imp_RtlCreateUnicodeString
0x180045504  test    al, al
0x180045506  jnz     short loc_18004551A
0x180045508  lea     r9, aErrorCopyingSt; "Error copying string table temp filenam"...
0x18004550f  mov     r8d, 19Bh
0x180045515  jmp     loc_18004545A
0x18004551a  lea     rcx, [rdi+0A58h]
0x180045521  cmp     [rcx], r14
0x180045524  jnz     short loc_180045541
0x180045526  call    AslHashCreate
0x18004552b  test    eax, eax
0x18004552d  jns     short loc_180045541
0x18004552f  lea     r9, aErrorCreatingH; "Error creating hash table [%x]"
0x180045536  mov     r8d, 1A4h
0x18004553c  jmp     loc_1800453E4
0x180045541  mov     r14d, 1
0x180045547  jmp     short loc_18004556C
0x180045549  lea     r9, aCouldnTGetTheM; "Couldn't get the .mui file path"
0x180045550  mov     r8d, 14Fh
0x180045556  lea     rdx, aSdbpaddstringt_0; "SdbpAddStringTableToPDB"
0x18004555d  mov     ecx, 1
0x180045562  call    AslLogCallPrintf
0x180045567  test    rbx, rbx
0x18004556a  jz      short loc_180045581
0x18004556c  mov     rcx, gs:60h
0x180045575  mov     rdx, rbx
0x180045578  mov     rcx, [rcx+30h]
0x18004557c  call    AslFree
0x180045581  mov     eax, r14d
0x180045584  mov     rcx, [rbp+3D0h+var_30]
0x18004558b  xor     rcx, rsp; StackCookie
0x18004558e  call    __security_check_cookie
0x180045593  lea     r11, [rsp+4D0h+var_20]
0x18004559b  mov     rbx, [r11+38h]
0x18004559f  mov     rsi, [r11+40h]
0x1800455a3  mov     rsp, r11
0x1800455a6  pop     r15
0x1800455a8  pop     r14
0x1800455aa  pop     r12
0x1800455ac  pop     rdi
0x1800455ad  pop     rbp
0x1800455ae  retn
```
