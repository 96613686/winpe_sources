# VfsCreateDirQueryContext

- ea: `0x1400074f4`
- end: `0x1400076c9`
- name: `VfsCreateDirQueryContext`
- size: `469`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140006710`

## callees

- `0x140007124`
- `0x1400073a4`
- `0x1400074f4`
- `0x140007a14`
- `0x140010bac`
- `0x140012acc`
- `0x140013b00`

## import_xrefs

- `FLTMGR!FltReleaseFileNameInformation` at `0x1400076a4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014bcc`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400076a4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014bcc`

## string_xrefs

- `0x1400075de`: `VfsCreateDirQueryContext() - Failed to get filename info for data: %p\n IRP: %d\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsCreateDirQueryContext(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rax
  void *v6; // r15
  int v7; // eax
  unsigned int v8; // ebx
  int SubContext; // edi
  PVOID v11; // rbx
  __int64 v12; // [rsp+20h] [rbp-98h]
  PVOID Entry; // [rsp+40h] [rbp-78h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+48h] [rbp-70h]
  int v15; // [rsp+50h] [rbp-68h]
  __int64 v16[2]; // [rsp+58h] [rbp-60h] BYREF
  __int128 v17; // [rsp+68h] [rbp-50h]
  __int128 v18; // [rsp+78h] [rbp-40h]

  Entry = 0;
  FileNameInformation = 0;
  *(_OWORD *)v16 = 0;
  v17 = 0;
  v18 = 0;
  if ( *(_WORD *)a2 == 5767 )
  {
    v5 = *(_QWORD *)(a2 + 24);
    v6 = (void *)(v5 + 152);
    v17 = *(_OWORD *)(v5 + 220);
    v18 = *(_OWORD *)(v5 + 236);
  }
  else
  {
    v6 = (void *)(a2 + 72);
    v17 = *(_OWORD *)(a2 + 40);
    v18 = *(_OWORD *)(a2 + 56);
  }
  v7 = VfsGetFileNameInformation(CallbackData, (__int64)v16);
  v8 = v7;
  if ( v7 >= 0 )
  {
    SubContext = VfsAllocateDirQueryContext((__int64)CallbackData, &Entry);
    v15 = SubContext;
    if ( SubContext >= 0 )
    {
      if ( LOWORD(v16[0]) == 2 && *(_WORD *)v16[1] == 92 )
        *(_DWORD *)Entry |= 2u;
      v11 = Entry;
      SubContext = VfsAddDirQuerySubContext(
                     v6,
                     (__int64)&FileNameInformation->Volume,
                     (__int64)&FileNameInformation->Name,
                     (__int64)Entry);
      v15 = SubContext;
      if ( SubContext >= 0 )
      {
        *a3 = v11;
        Entry = 0;
      }
    }
    FltReleaseFileNameInformation(FileNameInformation);
    if ( Entry )
      VfsDeleteDirQueryContext(Entry);
    return (unsigned int)SubContext;
  }
  else
  {
    LODWORD(v12) = CallbackData->Iopb->MajorFunction;
    LogWrite(
      1,
      0,
      L"VfsCreateDirQueryContext() - Failed to get filename info for data: %p\n IRP: %d\n Status: 0x%08X",
      CallbackData,
      v12,
      v7);
    return v8;
  }
}

```

## disassembly

```asm
0x1400074f4  mov     [rsp+arg_18], rbx
0x1400074f9  push    rsi
0x1400074fa  push    rdi
0x1400074fb  push    r12
0x1400074fd  push    r14
0x1400074ff  push    r15
0x140007501  sub     rsp, 90h
0x140007508  mov     rax, cs:__security_cookie
0x14000750f  xor     rax, rsp
0x140007512  mov     [rsp+0B8h+var_30], rax
0x14000751a  mov     r12, r8
0x14000751d  mov     rsi, rcx
0x140007520  mov     [rsp+0B8h+Entry], 0
0x140007529  mov     [rsp+0B8h+FileNameInformation], 0
0x140007532  xorps   xmm0, xmm0
0x140007535  movups  xmmword ptr [rsp+0B8h+var_60], xmm0
0x14000753a  xorps   xmm1, xmm1
0x14000753d  movups  [rsp+0B8h+var_50], xmm1
0x140007542  movups  [rsp+0B8h+var_40], xmm1
0x140007547  mov     eax, 1687h
0x14000754c  cmp     [rdx], ax
0x14000754f  jnz     short loc_140007589
0x140007551  xor     r14d, r14d
0x140007554  mov     rax, [rdx+18h]
0x140007558  lea     r15, [rax+98h]
0x14000755f  movups  xmm0, xmmword ptr [rax+0DCh]
0x140007566  movups  [rsp+0B8h+var_50], xmm0
0x14000756b  movups  xmm1, xmmword ptr [rax+0ECh]
0x140007572  movups  [rsp+0B8h+var_40], xmm1
0x140007577  mov     eax, [rdx+4]
0x14000757a  test    al, 4
0x14000757c  jz      short loc_140007582
0x14000757e  mov     r14, [rdx+30h]
0x140007582  mov     ecx, 1000101h
0x140007587  jmp     short loc_1400075AC
0x140007589  mov     ecx, 101h
0x14000758e  lea     r15, [rdx+48h]
0x140007592  movups  xmm0, xmmword ptr [rdx+28h]
0x140007596  movups  [rsp+0B8h+var_50], xmm0
0x14000759b  movups  xmm1, xmmword ptr [rdx+38h]
0x14000759f  movups  [rsp+0B8h+var_40], xmm1
0x1400075a4  mov     rax, [rsi+10h]
0x1400075a8  mov     r14, [rax+8]
0x1400075ac  lea     rax, [rsp+0B8h+var_60]
0x1400075b1  mov     [rsp+0B8h+var_98], rax; __int64
0x1400075b6  lea     r8, [rsp+0B8h+FileNameInformation]
0x1400075bb  mov     edx, ecx
0x1400075bd  mov     rcx, rsi; CallbackData
0x1400075c0  call    VfsGetFileNameInformation
0x1400075c5  mov     ebx, eax
0x1400075c7  test    eax, eax
0x1400075c9  jns     short loc_14000761A
0x1400075cb  mov     rcx, [rsi+10h]
0x1400075cf  movzx   edx, byte ptr [rcx+4]
0x1400075d3  mov     dword ptr [rsp+0B8h+var_90], eax
0x1400075d7  mov     dword ptr [rsp+0B8h+var_98], edx
0x1400075db  mov     r9, rsi
0x1400075de  lea     r8, aVfscreatedirqu_1; "VfsCreateDirQueryContext() - Failed to "...
0x1400075e5  xor     edx, edx
0x1400075e7  lea     ecx, [rdx+1]
0x1400075ea  call    LogWrite
0x1400075ef  mov     eax, ebx
0x1400075f1  mov     rcx, [rsp+0B8h+var_30]
0x1400075f9  xor     rcx, rsp; StackCookie
0x1400075fc  call    __security_check_cookie
0x140007601  mov     rbx, [rsp+0B8h+arg_18]
0x140007609  add     rsp, 90h
0x140007610  pop     r15
0x140007612  pop     r14
0x140007614  pop     r12
0x140007616  pop     rdi
0x140007617  pop     rsi
0x140007618  retn
0x14000761a  lea     rdx, [rsp+0B8h+Entry]
0x14000761f  mov     rcx, rsi
0x140007622  call    VfsAllocateDirQueryContext
0x140007627  mov     edi, eax
0x140007629  mov     [rsp+0B8h+var_68], eax
0x14000762d  test    eax, eax
0x14000762f  js      short loc_14000769F
0x140007631  mov     ecx, 2
0x140007636  cmp     word ptr [rsp+0B8h+var_60], cx
0x14000763b  jnz     short loc_14000764F
0x14000763d  mov     rax, [rsp+0B8h+var_60+8]
0x140007642  cmp     word ptr [rax], 5Ch ; '\'
0x140007646  jnz     short loc_14000764F
0x140007648  mov     rbx, [rsp+0B8h+Entry]
0x14000764d  or      [rbx], ecx
0x14000764f  mov     rax, [rsp+0B8h+FileNameInformation]
0x140007654  lea     rdx, [rax+8]
0x140007658  add     rax, 18h
0x14000765c  mov     r8, [rsi+10h]
0x140007660  mov     rbx, [rsp+0B8h+Entry]
0x140007665  mov     [rsp+0B8h+var_88], rbx; __int64
0x14000766a  mov     [rsp+0B8h+var_90], rdx; __int64
0x14000766f  mov     [rsp+0B8h+var_98], rax; __int64
0x140007674  mov     r9, r14
0x140007677  mov     r8, [r8+10h]
0x14000767b  lea     rdx, [rsp+0B8h+var_50]
0x140007680  mov     rcx, r15; Buffer
0x140007683  call    VfsAddDirQuerySubContext
0x140007688  mov     edi, eax
0x14000768a  mov     [rsp+0B8h+var_68], eax
0x14000768e  test    eax, eax
0x140007690  js      short loc_14000769F
0x140007692  mov     [r12], rbx
0x140007696  mov     [rsp+0B8h+Entry], 0
0x14000769f  mov     rcx, [rsp+0B8h+FileNameInformation]; FileNameInformation
0x1400076a4  call    cs:__imp_FltReleaseFileNameInformation
0x1400076ab  nop     dword ptr [rax+rax+00h]
0x1400076b0  mov     rbx, [rsp+0B8h+Entry]
0x1400076b5  test    rbx, rbx
0x1400076b8  jz      short loc_1400076C2
0x1400076ba  mov     rcx, rbx; Entry
0x1400076bd  call    VfsDeleteDirQueryContext
0x1400076c2  mov     eax, edi
0x1400076c4  jmp     loc_1400075F1
0x140014bbf  push    rbp
0x140014bc1  sub     rsp, 40h
0x140014bc5  mov     rbp, rdx
0x140014bc8  mov     rcx, [rbp+48h]; FileNameInformation
0x140014bcc  call    cs:__imp_FltReleaseFileNameInformation
0x140014bd3  nop     dword ptr [rax+rax+00h]
0x140014bd8  mov     rcx, [rbp+40h]; Entry
0x140014bdc  test    rcx, rcx
0x140014bdf  jz      short loc_140014BE7
0x140014be1  call    VfsDeleteDirQueryContext
0x140014be6  nop
0x140014be7  add     rsp, 40h
0x140014beb  pop     rbp
0x140014bec  retn
```
