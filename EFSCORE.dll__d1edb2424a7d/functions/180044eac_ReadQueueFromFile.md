# ReadQueueFromFile

- ea: `0x180044eac`
- end: `0x1800450b7`
- name: `ReadQueueFromFile`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180044190`

## callees

- `0x180044a94`
- `0x180044eac`
- `0x180062320`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800dddf0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180044f05`
- `msvcrt!swprintf_s` at `0x180044f05`
- `msvcrt!wcstok_s` at `0x180044fc9`
- `msvcrt!wcstok_s` at `0x180044fc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004507c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004507c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004508a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004508a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045071`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045071`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180044ffa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180044ffa`

## pseudocode

```c
__int64 __fastcall ReadQueueFromFile(__int64 a1, const unsigned __int16 *a2)
{
  wchar_t *v3; // rdi
  int v4; // ecx
  unsigned int UserFEQueueFromFile; // ebx
  int v6; // r8d
  int v7; // eax
  wchar_t *v8; // rax
  wchar_t *v9; // rbx
  int v10; // ecx
  HANDLE ProcessHeap; // rax
  char v13; // [rsp+20h] [rbp-268h]
  wchar_t *String; // [rsp+40h] [rbp-248h] BYREF
  PSID Sid; // [rsp+48h] [rbp-240h] BYREF
  wchar_t *Context; // [rsp+50h] [rbp-238h] BYREF
  wchar_t Buffer[264]; // [rsp+60h] [rbp-228h] BYREF

  Context = 0;
  v3 = 0;
  Sid = 0;
  String = 0;
  if ( swprintf_s(Buffer, 0x104u, L"%s\\%s", a1, a2) == -1 )
  {
    UserFEQueueFromFile = -2147024883;
    v13 = 120;
    v6 = -2147024883;
LABEL_3:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v6, 34, v13);
    goto LABEL_11;
  }
  fnEfsLogTrace1Strings(v4, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 34, 127);
  UserFEQueueFromFile = EfsStringDup(
                          &String,
                          a2,
                          EfsStringDupDefaultAllocate,
                          (void (*)(void *))EfsStringDupDefaultFree);
  v7 = fnEfsLogTrace1String1Dword(
         g_hPublisher,
         (unsigned int)EFS_TRACE_COMPLETE_EVENT,
         (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
         (unsigned int)&sourceString,
         UserFEQueueFromFile,
         34,
         127);
  v3 = String;
  if ( v7 >= 0 )
  {
    v8 = wcstok_s(String, L"_", &Context);
    v9 = v8;
    if ( !v8 )
    {
      v13 = -124;
LABEL_7:
      UserFEQueueFromFile = -2147024809;
      v6 = -2147024809;
      goto LABEL_3;
    }
    if ( !ConvertStringSidToSidW(v8, &Sid) )
    {
      v13 = -115;
      goto LABEL_7;
    }
    fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 34, 144);
    UserFEQueueFromFile = LoadUserFEQueueFromFile(v9, Buffer);
    fnEfsLogTrace1String1Dword(
      g_hPublisher,
      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
      (unsigned int)&sourceString,
      UserFEQueueFromFile,
      34,
      144);
  }
LABEL_11:
  LocalFree(Sid);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
  }
  return UserFEQueueFromFile;
}

```

## disassembly

```asm
0x180044eac  mov     [rsp+arg_10], rbx
0x180044eb1  mov     [rsp+arg_18], rsi
0x180044eb6  push    rdi
0x180044eb7  sub     rsp, 280h
0x180044ebe  mov     rax, cs:__security_cookie
0x180044ec5  xor     rax, rsp
0x180044ec8  mov     [rsp+288h+var_18], rax
0x180044ed0  mov     rbx, rdx
0x180044ed3  mov     [rsp+288h+var_268], rdx
0x180044ed8  mov     r9, rcx
0x180044edb  mov     [rsp+288h+Context], 0
0x180044ee4  xor     edi, edi
0x180044ee6  mov     [rsp+288h+Sid], 0
0x180044eef  mov     edx, 104h; BufferCount
0x180044ef4  mov     [rsp+288h+String], rdi
0x180044ef9  lea     rcx, [rsp+288h+Buffer]; Buffer
0x180044efe  lea     r8, aSS; "%s\\%s"
0x180044f05  call    cs:__imp_swprintf_s
0x180044f0b  cmp     eax, 0FFFFFFFFh
0x180044f0e  jnz     short loc_180044F3F
0x180044f10  mov     ebx, 8007000Dh
0x180044f15  mov     dword ptr [rsp+288h+var_268], 278h
0x180044f1d  lea     r9d, [rdi+22h]
0x180044f21  mov     r8d, 8007000Dh
0x180044f27  mov     rcx, cs:g_hPublisher
0x180044f2e  lea     rdx, EFS_TRACE_ERROR
0x180044f35  call    fnEfsLogTrace1
0x180044f3a  jmp     loc_18004506C
0x180044f3f  mov     esi, 22h ; '"'
0x180044f44  lea     r8, sourceString
0x180044f4b  mov     edi, 27Fh
0x180044f50  lea     rdx, EFS_TRACE_START_EVENT
0x180044f57  mov     r9d, esi
0x180044f5a  mov     dword ptr [rsp+288h+var_268], edi
0x180044f5e  call    fnEfsLogTrace1Strings
0x180044f63  lea     r9, EfsStringDupDefaultFree; void (*)(void *)
0x180044f6a  mov     rdx, rbx; unsigned __int16 *
0x180044f6d  lea     r8, EfsStringDupDefaultAllocate; void *(*)(unsigned __int64)
0x180044f74  lea     rcx, [rsp+288h+String]; unsigned __int16 **
0x180044f79  call    ?EfsStringDup@@YAJPEAPEAGPEBGP6APEAX_K@ZP6AXPEAX@Z@Z; EfsStringDup(ushort * *,ushort const *,void * (*)(unsigned __int64),void (*)(void *))
0x180044f7e  mov     rcx, cs:g_hPublisher
0x180044f85  lea     r9, sourceString
0x180044f8c  mov     [rsp+288h+var_258], edi
0x180044f90  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180044f97  mov     [rsp+288h+var_260], esi
0x180044f9b  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180044fa2  mov     dword ptr [rsp+288h+var_268], eax
0x180044fa6  mov     ebx, eax
0x180044fa8  call    fnEfsLogTrace1String1Dword
0x180044fad  mov     rdi, [rsp+288h+String]
0x180044fb2  test    eax, eax
0x180044fb4  js      loc_18004506C
0x180044fba  lea     r8, [rsp+288h+Context]; Context
0x180044fbf  mov     rcx, rdi; String
0x180044fc2  lea     rdx, asc_1800F1D04; "_"
0x180044fc9  call    cs:__imp_wcstok_s
0x180044fcf  mov     rbx, rax
0x180044fd2  test    rax, rax
0x180044fd5  jnz     short loc_180044FF2
0x180044fd7  mov     dword ptr [rsp+288h+var_268], 284h
0x180044fdf  mov     r9d, esi
0x180044fe2  mov     ebx, 80070057h
0x180044fe7  mov     r8d, 80070057h
0x180044fed  jmp     loc_180044F27
0x180044ff2  lea     rdx, [rsp+288h+Sid]; Sid
0x180044ff7  mov     rcx, rbx; StringSid
0x180044ffa  call    cs:__imp_ConvertStringSidToSidW
0x180045000  mov     r9d, esi
0x180045003  test    eax, eax
0x180045005  jnz     short loc_180045011
0x180045007  mov     dword ptr [rsp+288h+var_268], 28Dh
0x18004500f  jmp     short loc_180044FE2
0x180045011  lea     r8, sourceString
0x180045018  mov     dword ptr [rsp+288h+var_268], 290h
0x180045020  lea     rdx, EFS_TRACE_START_EVENT
0x180045027  call    fnEfsLogTrace1Strings
0x18004502c  lea     rdx, [rsp+288h+Buffer]
0x180045031  mov     rcx, rbx
0x180045034  call    LoadUserFEQueueFromFile
0x180045039  mov     rcx, cs:g_hPublisher
0x180045040  lea     r9, sourceString
0x180045047  mov     [rsp+288h+var_258], 290h
0x18004504f  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180045056  mov     [rsp+288h+var_260], esi
0x18004505a  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180045061  mov     dword ptr [rsp+288h+var_268], eax
0x180045065  mov     ebx, eax
0x180045067  call    fnEfsLogTrace1String1Dword
0x18004506c  mov     rcx, [rsp+288h+Sid]; hMem
0x180045071  call    cs:__imp_LocalFree
0x180045077  test    rdi, rdi
0x18004507a  jz      short loc_180045090
0x18004507c  call    cs:__imp_GetProcessHeap
0x180045082  mov     r8, rdi; lpMem
0x180045085  xor     edx, edx; dwFlags
0x180045087  mov     rcx, rax; hHeap
0x18004508a  call    cs:__imp_HeapFree
0x180045090  mov     eax, ebx
0x180045092  mov     rcx, [rsp+288h+var_18]
0x18004509a  xor     rcx, rsp; StackCookie
0x18004509d  call    __security_check_cookie
0x1800450a2  lea     r11, [rsp+288h+var_8]
0x1800450aa  mov     rbx, [r11+20h]
0x1800450ae  mov     rsi, [r11+28h]
0x1800450b2  mov     rsp, r11
0x1800450b5  pop     rdi
0x1800450b6  retn
```
