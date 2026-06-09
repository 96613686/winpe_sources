# AiComputeImageHashWithOffset

- ea: `0x180006f08`
- end: `0x18000726d`
- name: `AiComputeImageHashWithOffset`
- size: `869`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800061c8`

## callees

- `0x180003fd4`
- `0x180005b28`
- `0x180006f08`
- `0x180007274`
- `0x180007450`

## import_xrefs

- `ntdll!NtReadFile` at `0x180007138`
- `ntdll!NtReadFile` at `0x180007138`
- `ntdll!NtWaitForSingleObject` at `0x18000714f`
- `ntdll!NtWaitForSingleObject` at `0x18000714f`
- `ntdll!RtlFreeHeap` at `0x18000724a`
- `ntdll!RtlFreeHeap` at `0x18000724a`
- `bcrypt!BCryptFinishHash` at `0x1800071e0`
- `bcrypt!BCryptFinishHash` at `0x1800071e0`
- `bcrypt!BCryptHashData` at `0x18000717b`
- `bcrypt!BCryptHashData` at `0x18000717b`
- `bcrypt!BCryptCreateHash` at `0x18000708c`
- `bcrypt!BCryptCreateHash` at `0x18000708c`
- `bcrypt!BCryptGetProperty` at `0x18000701c`
- `bcrypt!BCryptGetProperty` at `0x18000704b`
- `bcrypt!BCryptGetProperty` at `0x18000701c`
- `bcrypt!BCryptGetProperty` at `0x18000704b`

## pseudocode

```c
__int64 __fastcall AiComputeImageHashWithOffset(
        void *a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  NTSTATUS Property; // ebx
  void *v7; // r13
  void *v10; // rax
  __int64 v11; // rdi
  int v12; // eax
  __int64 v13; // rdi
  BCRYPT_HASH_HANDLE *v14; // rsi
  UCHAR *v15; // rax
  unsigned int v16; // edi
  ULONG Length; // esi
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdi
  __int64 v21; // r12
  __int64 v22; // rdi
  ULONG v23; // r8d
  _DWORD v25[2]; // [rsp+58h] [rbp-29h]
  union _LARGE_INTEGER ByteOffset; // [rsp+60h] [rbp-21h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+68h] [rbp-19h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-11h] BYREF
  BCRYPT_HASH_HANDLE hHash[2]; // [rsp+80h] [rbp-1h] BYREF
  _DWORD cbOutput[14]; // [rsp+90h] [rbp+Fh]
  __int64 pbOutput; // [rsp+E0h] [rbp+5Fh] BYREF
  ULONG pcbResult; // [rsp+F0h] [rbp+6Fh] BYREF

  pbOutput = a2;
  Property = 0;
  v7 = 0;
  ByteOffset.QuadPart = 0;
  v10 = a1;
  IoStatusBlock = 0;
  v25[0] = 0;
  if ( *(_DWORD *)(a4 + 4) )
  {
    LODWORD(pbOutput) = 32;
    Property = AipCalcHashFromFileHandle(a1);
    if ( Property < 0 )
      goto LABEL_45;
    v11 = a6;
    v10 = a1;
    *(_DWORD *)(a6 + 4) = pbOutput;
  }
  else
  {
    v11 = a6;
  }
  if ( *(_DWORD *)(a4 + 8) )
  {
    LODWORD(pbOutput) = 32;
    Property = AipCalcHashFromFileHandle(v10);
    if ( Property < 0 )
      goto LABEL_45;
    *(_DWORD *)(v11 + 8) = pbOutput;
  }
  v12 = 0;
  v13 = 0;
  do
  {
    if ( !*(_DWORD *)(a4 + 4 * v13) )
      goto LABEL_18;
    LODWORD(pbOutput) = 0;
    pcbResult = 0;
    v14 = &hHash[3 * v13];
    *(_OWORD *)v14 = 0;
    v14[2] = 0;
    hObject = *(&AipAlgHandle + v13);
    Property = BCryptGetProperty(hObject, L"HashDigestLength", (PUCHAR)v14 + 16, 4u, &pcbResult, 0);
    if ( Property < 0 )
      goto LABEL_15;
    Property = BCryptGetProperty(hObject, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
    if ( Property < 0 )
      goto LABEL_15;
    v15 = (UCHAR *)AiAlloc((unsigned int)pbOutput);
    v14[1] = v15;
    if ( !v15 )
    {
      Property = -1073741801;
LABEL_15:
      AipDestroyHash(&hHash[3 * v13]);
      goto LABEL_16;
    }
    Property = BCryptCreateHash(hObject, &hHash[3 * v13], v15, pbOutput, 0, 0, 0);
    if ( Property < 0 )
      goto LABEL_15;
LABEL_16:
    if ( Property < 0 )
      goto LABEL_45;
    v25[v13] = 1;
    v12 = 1;
LABEL_18:
    v13 = (unsigned int)(v13 + 1);
  }
  while ( !(_DWORD)v13 );
  if ( !v12 )
  {
    Property = 0;
    goto LABEL_45;
  }
  v16 = 0x8000;
  v7 = (void *)AiAlloc(0x8000);
  if ( !v7 )
  {
    Property = -1073741801;
    goto LABEL_45;
  }
  ByteOffset.QuadPart = 0;
  if ( !a3 )
  {
LABEL_34:
    v21 = a6;
    v22 = 0;
    while ( 1 )
    {
      if ( *(_DWORD *)(4 * v22 + a4) )
      {
        LODWORD(pbOutput) = 32;
        v23 = cbOutput[6 * v22];
        if ( v23 > 0x20 )
        {
          Property = -1073741789;
          goto LABEL_45;
        }
        Property = BCryptFinishHash(hHash[3 * v22], (PUCHAR)(a5 + 32LL * (unsigned int)v22), v23, 0);
        if ( Property < 0 )
          goto LABEL_45;
        *(_DWORD *)(4 * v22 + v21) = cbOutput[6 * v22];
      }
      v22 = (unsigned int)(v22 + 1);
      if ( (_DWORD)v22 )
        goto LABEL_45;
    }
  }
  while ( 1 )
  {
    Length = a3;
    if ( v16 <= a3 )
      Length = v16;
    Property = NtReadFile(a1, 0, 0, 0, &IoStatusBlock, v7, Length, &ByteOffset, 0);
    if ( Property == 259 )
    {
      NtWaitForSingleObject(a1, 0, 0);
      Property = IoStatusBlock.Status;
    }
    if ( Property < 0 )
      break;
    v20 = 0;
    do
    {
      if ( *(_DWORD *)(a4 + 4 * v20) )
      {
        Property = BCryptHashData(hHash[3 * v20], (PUCHAR)v7, Length, 0);
        if ( Property < 0 )
          goto LABEL_45;
      }
      v20 = (unsigned int)(v20 + 1);
    }
    while ( !(_DWORD)v20 );
    v16 = Length;
    ByteOffset.QuadPart += Length;
    a3 -= Length;
    if ( !a3 )
      goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, (unsigned int)Property);
LABEL_45:
  if ( v25[0] )
    AipDestroyHash(hHash);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180006f08  mov     rax, rsp
0x180006f0b  mov     [rax+18h], rbx
0x180006f0f  mov     [rax+10h], rdx
0x180006f13  mov     [rax+8], rcx
0x180006f17  push    rbp
0x180006f18  push    rsi
0x180006f19  push    rdi
0x180006f1a  push    r12
0x180006f1c  push    r13
0x180006f1e  push    r14
0x180006f20  push    r15
0x180006f22  lea     rbp, [rax-4Fh]
0x180006f26  sub     rsp, 90h
0x180006f2d  mov     rsi, [rbp+47h+arg_20]
0x180006f31  xor     ebx, ebx
0x180006f33  xor     r13d, r13d
0x180006f36  mov     qword ptr [rbp+47h+var_68], rbx
0x180006f3a  xorps   xmm0, xmm0
0x180006f3d  mov     r15, r9
0x180006f40  mov     r14, r8
0x180006f43  mov     rax, rcx
0x180006f46  movups  xmmword ptr [rbp+47h+IoStatusBlock], xmm0
0x180006f4a  mov     [rbp+47h+var_70], ebx
0x180006f4d  cmp     [r9+4], ebx
0x180006f51  jz      short loc_180006F88
0x180006f53  lea     r8, [rsi+20h]
0x180006f57  mov     dword ptr [rbp+47h+pbOutput], 20h ; ' '
0x180006f5e  lea     r9, [rbp+47h+pbOutput]
0x180006f62  lea     rdx, a13143226; "1.3.14.3.2.26"
0x180006f69  call    AipCalcHashFromFileHandle
0x180006f6e  mov     ebx, eax
0x180006f70  test    eax, eax
0x180006f72  js      loc_180007229
0x180006f78  mov     rdi, [rbp+47h+arg_28]
0x180006f7c  mov     ecx, dword ptr [rbp+47h+pbOutput]
0x180006f7f  mov     rax, [rbp+47h+FileHandle]
0x180006f83  mov     [rdi+4], ecx
0x180006f86  jmp     short loc_180006F8C
0x180006f88  mov     rdi, [rbp+47h+arg_28]
0x180006f8c  cmp     [r15+8], r13d
0x180006f90  jz      short loc_180006FC0
0x180006f92  lea     r8, [rsi+40h]
0x180006f96  mov     dword ptr [rbp+47h+pbOutput], 20h ; ' '
0x180006f9d  lea     r9, [rbp+47h+pbOutput]
0x180006fa1  mov     rcx, rax; hFileIn
0x180006fa4  lea     rdx, a21684011013421; "2.16.840.1.101.3.4.2.1"
0x180006fab  call    AipCalcHashFromFileHandle
0x180006fb0  mov     ebx, eax
0x180006fb2  test    eax, eax
0x180006fb4  js      loc_180007229
0x180006fba  mov     eax, dword ptr [rbp+47h+pbOutput]
0x180006fbd  mov     [rdi+8], eax
0x180006fc0  xor     eax, eax
0x180006fc2  xor     edi, edi
0x180006fc4  cmp     [r15+rdi*4], r13d
0x180006fc8  jz      loc_1800070B5
0x180006fce  xor     edx, edx
0x180006fd0  lea     rax, [rdi+rdi*2]
0x180006fd4  xor     ecx, ecx
0x180006fd6  mov     [rsp+0C0h+dwFlags], edx; dwFlags
0x180006fda  xorps   xmm0, xmm0
0x180006fdd  mov     dword ptr [rbp+47h+pbOutput], edx
0x180006fe0  mov     [rbp+47h+arg_18], edx
0x180006fe3  lea     rsi, [rbp+47h+hHash]
0x180006fe7  lea     rsi, [rsi+rax*8]
0x180006feb  movups  xmmword ptr [rsi], xmm0
0x180006fee  mov     [rsi+10h], rcx
0x180006ff2  lea     r9d, [rdx+4]; cbOutput
0x180006ff6  lea     rcx, [rbp+47h+arg_18]
0x180006ffa  mov     [rsp+0C0h+pcbResult], rcx; pcbResult
0x180006fff  lea     rax, AipAlgHandle
0x180007006  mov     rax, [rax+rdi*8]
0x18000700a  lea     r8, [rsi+10h]; pbOutput
0x18000700e  mov     rcx, rax; hObject
0x180007011  mov     [rbp+47h+hObject], rax
0x180007015  lea     rdx, pszProperty; "HashDigestLength"
0x18000701c  call    cs:__imp_BCryptGetProperty
0x180007022  mov     ebx, eax
0x180007024  test    eax, eax
0x180007026  js      short loc_180007098
0x180007028  mov     rcx, [rbp+47h+hObject]; hObject
0x18000702c  lea     rax, [rbp+47h+arg_18]
0x180007030  mov     [rsp+0C0h+dwFlags], r13d; dwFlags
0x180007035  lea     r8, [rbp+47h+pbOutput]; pbOutput
0x180007039  mov     r9d, 4; cbOutput
0x18000703f  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x180007044  lea     rdx, aObjectlength; "ObjectLength"
0x18000704b  call    cs:__imp_BCryptGetProperty
0x180007051  mov     ebx, eax
0x180007053  test    eax, eax
0x180007055  js      short loc_180007098
0x180007057  mov     ecx, dword ptr [rbp+47h+pbOutput]
0x18000705a  call    AiAlloc
0x18000705f  xor     ecx, ecx
0x180007061  mov     [rsi+8], rax
0x180007065  test    rax, rax
0x180007068  jnz     short loc_180007071
0x18000706a  mov     ebx, 0C0000017h
0x18000706f  jmp     short loc_180007098
0x180007071  mov     r9d, dword ptr [rbp+47h+pbOutput]; cbHashObject
0x180007075  mov     r8, rax; pbHashObject
0x180007078  mov     [rsp+0C0h+Length], ecx; dwFlags
0x18000707c  mov     rdx, rsi; phHash
0x18000707f  mov     [rsp+0C0h+dwFlags], ecx; cbSecret
0x180007083  mov     [rsp+0C0h+pcbResult], rcx; pbSecret
0x180007088  mov     rcx, [rbp+47h+hObject]; hAlgorithm
0x18000708c  call    cs:__imp_BCryptCreateHash
0x180007092  mov     ebx, eax
0x180007094  test    eax, eax
0x180007096  jns     short loc_1800070A0
0x180007098  mov     rcx, rsi
0x18000709b  call    AipDestroyHash
0x1800070a0  test    ebx, ebx
0x1800070a2  js      loc_180007229
0x1800070a8  mov     [rbp+rdi*4+47h+var_70], 1
0x1800070b0  mov     eax, 1
0x1800070b5  inc     edi
0x1800070b7  cmp     edi, 1
0x1800070ba  jb      loc_180006FC4
0x1800070c0  test    eax, eax
0x1800070c2  jnz     short loc_1800070CB
0x1800070c4  xor     ebx, ebx
0x1800070c6  jmp     loc_180007229
0x1800070cb  mov     edi, 8000h
0x1800070d0  mov     ecx, edi
0x1800070d2  call    AiAlloc
0x1800070d7  mov     r13, rax
0x1800070da  test    rax, rax
0x1800070dd  jnz     short loc_1800070E9
0x1800070df  mov     ebx, 0C0000017h
0x1800070e4  jmp     loc_180007229
0x1800070e9  mov     qword ptr [rbp+47h+var_68], 0
0x1800070f1  test    r14, r14
0x1800070f4  jz      loc_1800071A3
0x1800070fa  mov     r12, [rbp+47h+FileHandle]
0x1800070fe  mov     qword ptr [rsp+40h], 0; Key
0x180007107  mov     esi, r14d
0x18000710a  mov     eax, edi
0x18000710c  mov     rcx, r12; FileHandle
0x18000710f  cmp     rax, r14
0x180007112  lea     rax, [rbp+47h+var_68]
0x180007116  mov     [rsp+0C0h+ByteOffset], rax; ByteOffset
0x18000711b  lea     rax, [rbp+47h+IoStatusBlock]
0x18000711f  cmovbe  esi, edi
0x180007122  xor     r9d, r9d; ApcContext
0x180007125  mov     [rsp+0C0h+Length], esi; Length
0x180007129  xor     r8d, r8d; ApcRoutine
0x18000712c  mov     qword ptr [rsp+0C0h+dwFlags], r13; Buffer
0x180007131  xor     edx, edx; Event
0x180007133  mov     [rsp+0C0h+pcbResult], rax; IoStatusBlock
0x180007138  call    cs:__imp_NtReadFile
0x18000713e  mov     ebx, eax
0x180007140  cmp     eax, 103h
0x180007145  jnz     short loc_180007158
0x180007147  xor     r8d, r8d; Timeout
0x18000714a  xor     edx, edx; Alertable
0x18000714c  mov     rcx, r12; Handle
0x18000714f  call    cs:__imp_NtWaitForSingleObject
0x180007155  mov     ebx, dword ptr [rbp+47h+IoStatusBlock]
0x180007158  test    ebx, ebx
0x18000715a  js      loc_1800071FD
0x180007160  xor     edi, edi
0x180007162  cmp     dword ptr [r15+rdi*4], 0
0x180007167  jz      short loc_18000718B
0x180007169  lea     rcx, [rdi+rdi*2]
0x18000716d  xor     r9d, r9d; dwFlags
0x180007170  mov     rcx, [rbp+rcx*8+47h+hHash]; hHash
0x180007175  mov     r8d, esi; cbInput
0x180007178  mov     rdx, r13; pbInput
0x18000717b  call    cs:__imp_BCryptHashData
0x180007181  mov     ebx, eax
0x180007183  test    eax, eax
0x180007185  js      loc_180007229
0x18000718b  inc     edi
0x18000718d  cmp     edi, 1
0x180007190  jb      short loc_180007162
0x180007192  mov     eax, esi
0x180007194  mov     edi, esi
0x180007196  add     qword ptr [rbp+47h+var_68], rax
0x18000719a  sub     r14, rax
0x18000719d  jnz     loc_1800070FE
0x1800071a3  mov     r12, [rbp+47h+arg_28]
0x1800071a7  xor     edi, edi
0x1800071a9  lea     r14, ds:0[rdi*4]
0x1800071b1  mov     edx, edi
0x1800071b3  cmp     dword ptr [r14+r15], 0
0x1800071b8  jz      short loc_1800071F4
0x1800071ba  lea     rsi, [rdi+rdi*2]
0x1800071be  mov     dword ptr [rbp+47h+pbOutput], 20h ; ' '
0x1800071c5  mov     r8d, [rbp+rsi*8+47h+cbOutput]; cbOutput
0x1800071ca  cmp     r8d, 20h ; ' '
0x1800071ce  ja      short loc_180007224
0x1800071d0  mov     rcx, [rbp+rsi*8+47h+hHash]; hHash
0x1800071d5  xor     r9d, r9d; dwFlags
0x1800071d8  shl     rdx, 5
0x1800071dc  add     rdx, [rbp+47h+arg_20]; pbOutput
0x1800071e0  call    cs:__imp_BCryptFinishHash
0x1800071e6  mov     ebx, eax
0x1800071e8  test    eax, eax
0x1800071ea  js      short loc_180007229
0x1800071ec  mov     eax, [rbp+rsi*8+47h+cbOutput]
0x1800071f0  mov     [r14+r12], eax
0x1800071f4  inc     edi
0x1800071f6  cmp     edi, 1
0x1800071f9  jb      short loc_1800071A9
0x1800071fb  jmp     short loc_180007229
0x1800071fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180007204  lea     rax, WPP_GLOBAL_Control
0x18000720b  cmp     rcx, rax
0x18000720e  jz      short loc_180007229
0x180007210  test    byte ptr [rcx+1Ch], 20h
0x180007214  jz      short loc_180007229
0x180007216  mov     rcx, [rcx+10h]
0x18000721a  mov     r9d, ebx
0x18000721d  call    WPP_SF_D
0x180007222  jmp     short loc_180007229
0x180007224  mov     ebx, 0C0000023h
0x180007229  cmp     [rbp+47h+var_70], 0
0x18000722d  jz      short loc_180007238
0x18000722f  lea     rcx, [rbp+47h+hHash]
0x180007233  call    AipDestroyHash
0x180007238  mov     rcx, gs:60h
0x180007241  mov     r8, r13; P
0x180007244  xor     edx, edx; Flags
0x180007246  mov     rcx, [rcx+30h]; HeapHandle
0x18000724a  call    cs:__imp_RtlFreeHeap
0x180007250  mov     eax, ebx
0x180007252  mov     rbx, [rsp+0C0h+arg_10]
0x18000725a  add     rsp, 90h
0x180007261  pop     r15
0x180007263  pop     r14
0x180007265  pop     r13
0x180007267  pop     r12
0x180007269  pop     rdi
0x18000726a  pop     rsi
0x18000726b  pop     rbp
0x18000726c  retn
```
