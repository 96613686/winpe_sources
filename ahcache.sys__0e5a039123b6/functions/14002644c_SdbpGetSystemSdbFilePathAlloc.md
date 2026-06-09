# SdbpGetSystemSdbFilePathAlloc

- ea: `0x14002644c`
- end: `0x140026548`
- name: `SdbpGetSystemSdbFilePathAlloc`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14002642c`

## callees

- `0x1400079f0`
- `0x140007e40`
- `0x14002644c`
- `0x14003e364`
- `0x14003e76c`
- `0x140042fec`
- `0x140045d44`

## string_xrefs

- `0x1400264bc`: `SdbpGetSystemSdbFilePath failed [%x]`
- `0x1400264c9`: `SdbpGetSystemSdbFilePathAlloc`

## pseudocode

```c
__int64 __fastcall SdbpGetSystemSdbFilePathAlloc(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rdx
  __int64 v7; // r9
  int SystemSdbFilePath; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 v11; // r8
  __int64 v12; // rcx
  void *v13; // rdx
  __int64 v15; // [rsp+20h] [rbp-248h]
  void *v16; // [rsp+30h] [rbp-238h] BYREF
  wchar_t v17[264]; // [rsp+40h] [rbp-228h] BYREF

  memset(v17, 0, 0x208u);
  v16 = 0;
  *a1 = 0;
  SystemSdbFilePath = SdbpGetSystemSdbFilePath(v17, v6, 1, v7, 0, a5);
  v9 = SystemSdbFilePath;
  if ( SystemSdbFilePath < 0 )
  {
    v10 = "SdbpGetSystemSdbFilePath failed [%x]";
    v11 = 1448;
LABEL_3:
    LODWORD(v15) = SystemSdbFilePath;
    AslLogCallPrintf(1, "SdbpGetSystemSdbFilePathAlloc", v11, v10, v15);
    v13 = v16;
    goto LABEL_7;
  }
  SystemSdbFilePath = AslStringDuplicate(&v16, v17);
  v9 = SystemSdbFilePath;
  if ( SystemSdbFilePath < 0 )
  {
    v10 = "AslStringDuplicate failed [%x]";
    v11 = 1455;
    goto LABEL_3;
  }
  v13 = 0;
  *a1 = v16;
  v9 = 0;
  v16 = 0;
LABEL_7:
  if ( v13 )
    AslFree(v12, v13);
  return v9;
}

```

## disassembly

```asm
0x14002644c  mov     [rsp+arg_8], rbx
0x140026451  push    rdi
0x140026452  sub     rsp, 260h
0x140026459  mov     rax, cs:__security_cookie
0x140026460  xor     rax, rsp
0x140026463  mov     [rsp+268h+var_18], rax
0x14002646b  mov     rbx, [rsp+268h+arg_20]
0x140026473  mov     rdi, rcx
0x140026476  lea     rcx, [rsp+268h+var_228]; void *
0x14002647b  xor     edx, edx; Val
0x14002647d  mov     r8d, 208h; Size
0x140026483  call    memset
0x140026488  mov     r8d, 1
0x14002648e  mov     [rsp+268h+var_240], rbx
0x140026493  lea     rcx, [rsp+268h+var_228]
0x140026498  mov     [rsp+268h+var_238], 0
0x1400264a1  mov     qword ptr [rdi], 0
0x1400264a8  mov     [rsp+268h+var_248], 0
0x1400264b1  call    SdbpGetSystemSdbFilePath
0x1400264b6  mov     ebx, eax
0x1400264b8  test    eax, eax
0x1400264ba  jns     short loc_1400264E5
0x1400264bc  lea     r9, aSdbpgetsystems; "SdbpGetSystemSdbFilePath failed [%x]"
0x1400264c3  mov     r8d, 5A8h
0x1400264c9  lea     rdx, aSdbpgetsystems_0; "SdbpGetSystemSdbFilePathAlloc"
0x1400264d0  mov     dword ptr [rsp+268h+var_248], eax
0x1400264d4  mov     ecx, 1
0x1400264d9  call    AslLogCallPrintf
0x1400264de  mov     rdx, [rsp+268h+var_238]
0x1400264e3  jmp     short loc_14002651A
0x1400264e5  lea     rdx, [rsp+268h+var_228]
0x1400264ea  lea     rcx, [rsp+268h+var_238]
0x1400264ef  call    AslStringDuplicate
0x1400264f4  mov     ebx, eax
0x1400264f6  test    eax, eax
0x1400264f8  jns     short loc_140026509
0x1400264fa  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x140026501  mov     r8d, 5AFh
0x140026507  jmp     short loc_1400264C9
0x140026509  mov     rax, [rsp+268h+var_238]
0x14002650e  xor     edx, edx
0x140026510  mov     [rdi], rax
0x140026513  xor     ebx, ebx
0x140026515  mov     [rsp+268h+var_238], rdx
0x14002651a  test    rdx, rdx
0x14002651d  jz      short loc_140026524
0x14002651f  call    AslFree
0x140026524  mov     eax, ebx
0x140026526  mov     rcx, [rsp+268h+var_18]
0x14002652e  xor     rcx, rsp; StackCookie
0x140026531  call    __security_check_cookie
0x140026536  mov     rbx, [rsp+268h+arg_8]
0x14002653e  add     rsp, 260h
0x140026545  pop     rdi
0x140026546  retn
```
