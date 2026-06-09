# PrjfSendGetFileStreamCommand

- ea: `0x1400349fc`
- end: `0x140034c68`
- name: `PrjfSendGetFileStreamCommand`
- size: `620`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140028b30`

## callees

- `0x140002b50`
- `0x14000be80`
- `0x14000d754`
- `0x140032db4`
- `0x140033bd0`
- `0x1400349fc`
- `0x14003a5cc`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140034c29`
- `FLTMGR!FltReleaseContext` at `0x140034c3d`
- `FLTMGR!FltReleaseContext` at `0x140034c29`
- `FLTMGR!FltReleaseContext` at `0x140034c3d`

## pseudocode

```c
__int64 __fastcall PrjfSendGetFileStreamCommand(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        _QWORD *a3,
        unsigned int a4,
        int a5)
{
  int v9; // eax
  int v10; // edx
  int v11; // r8d
  _DWORD *v12; // r14
  int v13; // ebx
  int v14; // edx
  int v15; // r8d
  __int64 v17; // [rsp+20h] [rbp-E0h]
  PVOID Entry[2]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v19[34]; // [rsp+80h] [rbp-80h] BYREF
  int v20; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned int v21; // [rsp+2E8h] [rbp+1E8h] BYREF

  Entry[0] = 0;
  memset(v19, 0, sizeof(v19));
  v21 = 0;
  v20 = 0;
  a5 = 4;
  *((_QWORD *)&v19[0] + 1) = a4;
  if ( a3 )
    *(_QWORD *)&v19[0] = *a3;
  v9 = PrjfPrepareCommandForFileObject(Instance, FileObject, 6, v19, v17, Entry, &v21);
  v12 = Entry[0];
  v13 = v9;
  if ( v9 >= 0 )
  {
    if ( (unsigned __int8)PrjfGetContextFileObject(Instance, FileObject) )
    {
      v13 = PrjfSendCommand(0, Instance, v12, MEMORY[0x58] + 40LL, (__int64)&v20, &a5);
      if ( v13 < 0
        && ((BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 0x40;
        LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          526,
          v14,
          v15,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          173,
          (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
          76,
          v13,
          (__int64)&FileObject->FileName);
      }
    }
  }
  else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = BYTE1(xmmword_14001A3D0) & 0x40;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDdZ(
      526,
      v10,
      v11,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      14,
      172,
      (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      49,
      v9,
      (__int64)&FileObject->FileName);
  }
  if ( v12 )
    PrjfFreeCommandBuffer(v12, v21);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400349fc  mov     [rsp-8+arg_0], rbx
0x140034a01  mov     [rsp-8+arg_8], rsi
0x140034a06  push    rbp
0x140034a07  push    rdi
0x140034a08  push    r13
0x140034a0a  push    r14
0x140034a0c  push    r15
0x140034a0e  lea     rbp, [rsp-1A0h]
0x140034a16  sub     rsp, 2A0h
0x140034a1d  mov     r14, r8
0x140034a20  mov     [rsp+2C0h+Entry], 0
0x140034a29  mov     r13, rdx
0x140034a2c  mov     r15, rcx
0x140034a2f  xor     edx, edx; Val
0x140034a31  lea     rcx, [rbp+1C0h+var_240]; void *
0x140034a35  mov     r8d, 220h; Size
0x140034a3b  mov     ebx, r9d
0x140034a3e  call    memset
0x140034a43  xor     esi, esi
0x140034a45  mov     [rbp+1C0h+arg_18], 0
0x140034a4f  xor     edi, edi
0x140034a51  mov     [rbp+1C0h+arg_10], 0
0x140034a5b  mov     [rbp+1C0h+arg_20], 4
0x140034a65  mov     [rsp+2C0h+var_260], rsi
0x140034a6a  mov     [rsp+2C0h+var_258], rdi
0x140034a6f  mov     [rbp+1C0h+var_238], ebx
0x140034a72  mov     [rbp+1C0h+var_234], esi
0x140034a75  test    r14, r14
0x140034a78  jz      short loc_140034A81
0x140034a7a  mov     rax, [r14]
0x140034a7d  mov     [rbp+1C0h+var_240], rax
0x140034a81  lea     rax, [rbp+1C0h+arg_18]
0x140034a88  mov     r8d, 6
0x140034a8e  mov     [rsp+2C0h+var_290], rax
0x140034a93  lea     r9, [rbp+1C0h+var_240]
0x140034a97  lea     rax, [rsp+2C0h+Entry]
0x140034a9c  mov     rdx, r13
0x140034a9f  mov     rcx, r15
0x140034aa2  mov     [rsp+2C0h+var_298], rax
0x140034aa7  call    PrjfPrepareCommandForFileObject
0x140034aac  mov     r14, [rsp+2C0h+Entry]
0x140034ab1  mov     ebx, eax
0x140034ab3  test    eax, eax
0x140034ab5  jns     loc_140034B3C
0x140034abb  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140034ac1  lea     rax, WPP_RECORDER_INITIALIZED
0x140034ac8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034acf  setnz   r8b
0x140034ad3  and     dl, 40h
0x140034ad6  jnz     short loc_140034AE1
0x140034ad8  test    r8b, r8b
0x140034adb  jz      loc_140034C0E
0x140034ae1  mov     r9, cs:WPP_GLOBAL_Control
0x140034ae8  lea     rax, [r13+58h]
0x140034aec  mov     [rsp+2C0h+var_268], rax
0x140034af1  mov     ecx, 20Eh
0x140034af6  mov     [rsp+2C0h+var_270], ebx
0x140034afa  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140034b01  mov     [rsp+2C0h+var_278], 1431h
0x140034b09  mov     r9, [r9+40h]
0x140034b0d  mov     [rsp+2C0h+var_280], rax
0x140034b12  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140034b19  mov     [rsp+2C0h+var_288], rax
0x140034b1e  mov     word ptr [rsp+2C0h+var_290], 0ACh
0x140034b25  mov     dword ptr [rsp+2C0h+var_298], 0Eh
0x140034b2d  mov     byte ptr [rsp+2C0h+var_2A0], 2
0x140034b32  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140034b37  jmp     loc_140034C0E
0x140034b3c  lea     r9, [rsp+2C0h+var_258]
0x140034b41  mov     rdx, r13; FileObject
0x140034b44  lea     r8, [rsp+2C0h+var_260]
0x140034b49  mov     rcx, r15; Instance
0x140034b4c  call    PrjfGetContextFileObject
0x140034b51  mov     rsi, [rsp+2C0h+var_260]
0x140034b56  test    al, al
0x140034b58  jz      loc_140034C09
0x140034b5e  mov     r9, [rsi+58h]
0x140034b62  lea     rax, [rbp+1C0h+arg_20]
0x140034b69  mov     [rsp+2C0h+var_298], rax
0x140034b6e  add     r9, 28h ; '('
0x140034b72  lea     rax, [rbp+1C0h+arg_10]
0x140034b79  mov     r8, r14
0x140034b7c  mov     rdx, r15
0x140034b7f  mov     [rsp+2C0h+var_2A0], rax
0x140034b84  xor     ecx, ecx
0x140034b86  call    PrjfSendCommand
0x140034b8b  mov     ebx, eax
0x140034b8d  test    eax, eax
0x140034b8f  jns     short loc_140034C09
0x140034b91  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140034b97  lea     rax, WPP_RECORDER_INITIALIZED
0x140034b9e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034ba5  setnz   r8b
0x140034ba9  and     dl, 40h
0x140034bac  jnz     short loc_140034BB3
0x140034bae  test    r8b, r8b
0x140034bb1  jz      short loc_140034C09
0x140034bb3  mov     r9, cs:WPP_GLOBAL_Control
0x140034bba  lea     rax, [r13+58h]
0x140034bbe  mov     [rsp+2C0h+var_268], rax
0x140034bc3  mov     ecx, 20Eh
0x140034bc8  mov     [rsp+2C0h+var_270], ebx
0x140034bcc  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140034bd3  mov     [rsp+2C0h+var_278], 144Ch
0x140034bdb  mov     r9, [r9+40h]
0x140034bdf  mov     [rsp+2C0h+var_280], rax
0x140034be4  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140034beb  mov     [rsp+2C0h+var_288], rax
0x140034bf0  mov     word ptr [rsp+2C0h+var_290], 0ADh
0x140034bf7  mov     dword ptr [rsp+2C0h+var_298], 0Eh
0x140034bff  mov     byte ptr [rsp+2C0h+var_2A0], 2
0x140034c04  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140034c09  mov     rdi, [rsp+2C0h+var_258]
0x140034c0e  test    r14, r14
0x140034c11  jz      short loc_140034C21
0x140034c13  mov     edx, [rbp+1C0h+arg_18]
0x140034c19  mov     rcx, r14; Entry
0x140034c1c  call    PrjfFreeCommandBuffer
0x140034c21  test    rsi, rsi
0x140034c24  jz      short loc_140034C35
0x140034c26  mov     rcx, rsi; Context
0x140034c29  call    cs:__imp_FltReleaseContext
0x140034c30  nop     dword ptr [rax+rax+00h]
0x140034c35  test    rdi, rdi
0x140034c38  jz      short loc_140034C49
0x140034c3a  mov     rcx, rdi; Context
0x140034c3d  call    cs:__imp_FltReleaseContext
0x140034c44  nop     dword ptr [rax+rax+00h]
0x140034c49  lea     r11, [rsp+2C0h+var_20]
0x140034c51  mov     eax, ebx
0x140034c53  mov     rbx, [r11+30h]
0x140034c57  mov     rsi, [r11+38h]
0x140034c5b  mov     rsp, r11
0x140034c5e  pop     r15
0x140034c60  pop     r14
0x140034c62  pop     r13
0x140034c64  pop     rdi
0x140034c65  pop     rbp
0x140034c66  retn
```
