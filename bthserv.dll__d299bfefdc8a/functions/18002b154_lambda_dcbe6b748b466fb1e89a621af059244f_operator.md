# _lambda_dcbe6b748b466fb1e89a621af059244f_::operator()

- ea: `0x18002b154`
- end: `0x18002b400`
- name: `_lambda_dcbe6b748b466fb1e89a621af059244f_::operator()`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18002afa4`

## callees

- `0x180001b60`
- `0x1800024ac`
- `0x180002834`
- `0x180010cac`
- `0x180011194`
- `0x180022688`
- `0x18002afc4`
- `0x18002b154`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b1c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b1c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b257`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b1da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b1da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b1d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b3d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b1d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b3d9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002b249`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002b249`

## string_xrefs

- `0x18002b3ee`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingnvramdatareader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int __fastcall lambda_dcbe6b748b466fb1e89a621af059244f_::operator()(__int64 *a1)
{
  __int64 *v2; // rax
  __int64 v3; // rcx
  char v4; // r12
  __int64 v5; // r15
  void *v6; // r14
  DWORD LastError; // ebx
  const char *v8; // r9
  unsigned __int16 v9; // r14
  unsigned __int16 *v10; // rsi
  signed int v11; // eax
  int v12; // r8d
  unsigned int v13; // ecx
  _DWORD *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // r14
  unsigned __int64 v17; // rbx
  __int64 v18; // r15
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rbx
  int v21; // r8d
  __int128 v22; // xmm1
  __int64 v23; // rcx
  int result; // eax
  int lpOutBuffer; // [rsp+20h] [rbp-50h]
  int lpOutBuffera; // [rsp+20h] [rbp-50h]
  DWORD nOutBufferSize; // [rsp+28h] [rbp-48h]
  _BYTE v28[25]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  DWORD BytesReturned; // [rsp+B0h] [rbp+40h] BYREF
  HANDLE hDevice; // [rsp+B8h] [rbp+48h] BYREF
  unsigned __int16 *v32; // [rsp+C0h] [rbp+50h]

  v2 = (__int64 *)*a1;
  v3 = *(_QWORD *)*a1;
  if ( v3 != v2[1] )
    v2[1] = v3;
  hDevice = (HANDLE)-1LL;
  *(_OWORD *)v28 = (unsigned __int64)&hDevice;
  v4 = 1;
  v28[16] = 1;
  *(_DWORD *)a1[1] = BthDevnodeOpenInterfaceHandle(v3, 0, &v28[8]);
  if ( v28[16] )
  {
    v5 = *(_QWORD *)&v28[8];
    v6 = **(void ***)v28;
    if ( (unsigned __int64)(**(_QWORD **)v28 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v6);
      SetLastError(LastError);
    }
    **(_QWORD **)v28 = v5;
  }
  v8 = (const char *)*(unsigned int *)a1[1];
  if ( (int)v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A,
      (int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingnvramdatareader.cpp",
      v8,
      lpOutBuffer);
  v9 = 4;
  while ( 1 )
  {
    v10 = (unsigned __int16 *)operator new[](25 * ((unsigned int)v9 - 1) + 27);
    v32 = v10;
    BytesReturned = 0;
    if ( DeviceIoControl(hDevice, 0x4111D0u, 0, 0, v10, 25 * (v9 - 1) + 27, &BytesReturned, 0) )
      break;
    v11 = GetLastError();
    v13 = v11;
    if ( v11 > 0 )
      v13 = (unsigned __int16)v11 | 0x80070000;
    *(_DWORD *)a1[1] = v13;
    v14 = (_DWORD *)a1[1];
    v15 = (unsigned int)*v14;
    if ( (_DWORD)v15 != -2147024774 || *v10 <= v9 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        v4 = 0;
      if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = v4;
        LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          v12,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          lpOutBuffera,
          nOutBufferSize,
          11,
          (__int64)WPP_26b232c2825f3d06e75e37d988803d66_Traceguids);
      }
      goto LABEL_33;
    }
    v9 = *v10;
    *v14 = 0;
    operator delete(v10, (const struct std::nothrow_t *)v15);
    if ( *(int *)a1[1] < 0 )
      goto LABEL_34;
  }
  v16 = (__int64 *)*a1;
  v17 = *v10;
  v18 = *(_QWORD *)(*a1 + 8);
  v15 = 0x8F5C28F5C28F5C29uLL;
  v19 = 0x8F5C28F5C28F5C29uLL * (v18 - *(_QWORD *)*a1);
  if ( v17 >= v19 )
  {
    if ( v17 > v19 )
    {
      if ( v17 <= 0x8F5C28F5C28F5C29uLL * (v16[2] - *v16) )
      {
        v20 = v17 - v19;
        if ( v20 )
        {
          LOBYTE(v15) = 0;
          memset_0(*(void **)(*a1 + 8), v15, 25 * v20);
          do
          {
            v18 += 25;
            --v20;
          }
          while ( v20 );
        }
        v16[1] = v18;
      }
      else
      {
        std::vector<BTHLE_PREPAIRING_ENTRY>::_Resize_reallocate<std::_Value_init_tag>(*a1, *v10);
      }
    }
  }
  else
  {
    v16[1] = *v16 + 25 * v17;
  }
  v21 = 0;
  if ( *v10 )
  {
    do
    {
      v15 = 25LL * v21;
      *(_OWORD *)v28 = *(_OWORD *)((char *)v10 + v15 + 2);
      *(_OWORD *)&v28[9] = *(_OWORD *)((char *)v10 + v15 + 11);
      v22 = *(_OWORD *)&v28[9];
      v23 = *(_QWORD *)*a1;
      *(_OWORD *)(v23 + v15) = *(_OWORD *)v28;
      *(_OWORD *)(v23 + v15 + 9) = v22;
      ++v21;
    }
    while ( v21 < *v10 );
  }
LABEL_33:
  operator delete(v10, (const struct std::nothrow_t *)v15);
LABEL_34:
  result = (_DWORD)hDevice - 1;
  if ( (char *)hDevice - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    return CloseHandle(hDevice);
  return result;
}

```

## disassembly

```asm
0x18002b154  push    rbp
0x18002b156  push    rbx
0x18002b157  push    rsi
0x18002b158  push    rdi
0x18002b159  push    r12
0x18002b15b  push    r14
0x18002b15d  push    r15
0x18002b15f  mov     rbp, rsp
0x18002b162  sub     rsp, 70h
0x18002b166  mov     rdi, rcx
0x18002b169  mov     rax, [rcx]
0x18002b16c  mov     rcx, [rax]
0x18002b16f  cmp     rcx, [rax+8]
0x18002b173  jz      short loc_18002B179
0x18002b175  mov     [rax+8], rcx
0x18002b179  mov     [rbp+hDevice], 0FFFFFFFFFFFFFFFFh
0x18002b181  lea     rax, [rbp+hDevice]
0x18002b185  mov     qword ptr [rbp+var_20], rax
0x18002b189  mov     qword ptr [rbp+var_20+8], 0
0x18002b191  mov     r12d, 1
0x18002b197  mov     [rbp+var_10], r12b
0x18002b19b  lea     r8, [rbp+var_20+8]
0x18002b19f  xor     edx, edx
0x18002b1a1  call    BthDevnodeOpenInterfaceHandle
0x18002b1a6  mov     rcx, [rdi+8]
0x18002b1aa  mov     [rcx], eax
0x18002b1ac  cmp     [rbp+var_10], 0
0x18002b1b0  jz      short loc_18002B1E3
0x18002b1b2  mov     r15, qword ptr [rbp+var_20+8]
0x18002b1b6  mov     rsi, qword ptr [rbp+var_20]
0x18002b1ba  mov     r14, [rsi]
0x18002b1bd  lea     rax, [r14-1]
0x18002b1c1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002b1c5  ja      short loc_18002B1E0
0x18002b1c7  call    cs:__imp_GetLastError
0x18002b1cd  mov     ebx, eax
0x18002b1cf  mov     rcx, r14; hObject
0x18002b1d2  call    cs:__imp_CloseHandle
0x18002b1d8  mov     ecx, ebx; dwErrCode
0x18002b1da  call    cs:__imp_SetLastError
0x18002b1e0  mov     [rsi], r15
0x18002b1e3  mov     rax, [rdi+8]
0x18002b1e7  mov     r9d, [rax]; char *
0x18002b1ea  mov     rcx, [rbp+38h]; this
0x18002b1ee  test    r9d, r9d
0x18002b1f1  js      loc_18002B3EE
0x18002b1f7  mov     r14d, 4
0x18002b1fd  movzx   eax, r14w
0x18002b201  sub     eax, r12d
0x18002b204  imul    ebx, eax, 19h
0x18002b207  add     ebx, 1Bh
0x18002b20a  mov     ecx, ebx; unsigned __int64
0x18002b20c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002b211  mov     rsi, rax
0x18002b214  mov     [rbp+arg_10], rax
0x18002b218  mov     [rbp+BytesReturned], 0
0x18002b21f  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x18002b228  lea     rax, [rbp+BytesReturned]
0x18002b22c  mov     [rsp+70h+lpBytesReturned], rax; lpBytesReturned
0x18002b231  mov     [rsp+70h+nOutBufferSize], ebx; nOutBufferSize
0x18002b235  mov     [rsp+70h+lpOutBuffer], rsi; lpOutBuffer
0x18002b23a  xor     r9d, r9d; nInBufferSize
0x18002b23d  xor     r8d, r8d; lpInBuffer
0x18002b240  mov     edx, 4111D0h; dwIoControlCode
0x18002b245  mov     rcx, [rbp+hDevice]; hDevice
0x18002b249  call    cs:__imp_DeviceIoControl
0x18002b24f  test    eax, eax
0x18002b251  jnz     loc_18002B312
0x18002b257  call    cs:__imp_GetLastError
0x18002b25d  mov     ecx, eax
0x18002b25f  test    eax, eax
0x18002b261  jle     short loc_18002B26C
0x18002b263  movzx   ecx, ax
0x18002b266  or      ecx, 80070000h
0x18002b26c  mov     rax, [rdi+8]
0x18002b270  mov     [rax], ecx
0x18002b272  mov     rax, [rdi+8]
0x18002b276  mov     edx, [rax]; struct std::nothrow_t *
0x18002b278  cmp     edx, 8007007Ah
0x18002b27e  jnz     short loc_18002B2AA
0x18002b280  cmp     [rsi], r14w
0x18002b284  jbe     short loc_18002B2AA
0x18002b286  movzx   r14d, word ptr [rsi]
0x18002b28a  mov     dword ptr [rax], 0
0x18002b290  mov     rcx, rsi; void *
0x18002b293  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b298  mov     rax, [rdi+8]
0x18002b29c  cmp     dword ptr [rax], 0
0x18002b29f  jge     loc_18002B1FD
0x18002b2a5  jmp     loc_18002B3CB
0x18002b2aa  lea     rax, WPP_GLOBAL_Control
0x18002b2b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b2b8  cmp     rcx, rax
0x18002b2bb  jz      short loc_18002B2C3
0x18002b2bd  cmp     byte ptr [rcx+19h], 2
0x18002b2c1  jnb     short loc_18002B2C6
0x18002b2c3  xor     r12b, r12b
0x18002b2c6  lea     rax, WPP_RECORDER_INITIALIZED
0x18002b2cd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002b2d4  setnz   r8b
0x18002b2d8  test    r12b, r12b
0x18002b2db  jnz     short loc_18002B2E6
0x18002b2dd  test    r8b, r8b
0x18002b2e0  jz      loc_18002B3C2
0x18002b2e6  mov     [rsp+70h+var_28], edx
0x18002b2ea  lea     rax, WPP_26b232c2825f3d06e75e37d988803d66_Traceguids
0x18002b2f1  mov     [rsp+70h+lpOverlapped], rax
0x18002b2f6  mov     word ptr [rsp+70h+lpBytesReturned], 0Bh
0x18002b2fd  mov     r9, [rcx+28h]
0x18002b301  mov     dl, r12b
0x18002b304  mov     rcx, [rcx+10h]
0x18002b308  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002b30d  jmp     loc_18002B3C2
0x18002b312  mov     r14, [rdi]
0x18002b315  movzx   ebx, word ptr [rsi]
0x18002b318  mov     r15, [r14+8]
0x18002b31c  mov     rcx, r15
0x18002b31f  sub     rcx, [r14]
0x18002b322  mov     rdx, 8F5C28F5C28F5C29h
0x18002b32c  imul    rcx, rdx
0x18002b330  cmp     rbx, rcx
0x18002b333  jnb     short loc_18002B342
0x18002b335  imul    rax, rbx, 19h
0x18002b339  add     rax, [r14]
0x18002b33c  mov     [r14+8], rax
0x18002b340  jmp     short loc_18002B381
0x18002b342  jbe     short loc_18002B381
0x18002b344  mov     rax, [r14+10h]
0x18002b348  sub     rax, [r14]
0x18002b34b  imul    rax, rdx
0x18002b34f  cmp     rbx, rax
0x18002b352  jbe     short loc_18002B361
0x18002b354  mov     rdx, rbx
0x18002b357  mov     rcx, r14
0x18002b35a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UBTHLE_PREPAIRING_ENTRY@@V?$allocator@UBTHLE_PREPAIRING_ENTRY@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<BTHLE_PREPAIRING_ENTRY>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002b35f  jmp     short loc_18002B381
0x18002b361  sub     rbx, rcx
0x18002b364  jz      short loc_18002B37D
0x18002b366  imul    r8, rbx, 19h; Size
0x18002b36a  xor     dl, dl; Val
0x18002b36c  mov     rcx, r15; void *
0x18002b36f  call    memset_0
0x18002b374  add     r15, 19h
0x18002b378  sub     rbx, r12
0x18002b37b  jnz     short loc_18002B374
0x18002b37d  mov     [r14+8], r15
0x18002b381  xor     r8d, r8d
0x18002b384  xor     eax, eax
0x18002b386  cmp     ax, [rsi]
0x18002b389  jnb     short loc_18002B3C2
0x18002b38b  movsxd  rax, r8d
0x18002b38e  imul    rdx, rax, 19h; struct std::nothrow_t *
0x18002b392  movups  xmm0, xmmword ptr [rdx+rsi+2]
0x18002b397  movups  [rbp+var_20], xmm0
0x18002b39b  movups  xmm1, xmmword ptr [rdx+rsi+0Bh]
0x18002b3a0  movups  [rbp+var_20+9], xmm1
0x18002b3a4  mov     rax, [rdi]
0x18002b3a7  mov     rcx, [rax]
0x18002b3aa  movups  xmm0, [rbp+var_20]
0x18002b3ae  movups  xmmword ptr [rcx+rdx], xmm0
0x18002b3b2  movups  xmmword ptr [rcx+rdx+9], xmm1
0x18002b3b7  add     r8d, r12d
0x18002b3ba  movzx   eax, word ptr [rsi]
0x18002b3bd  cmp     r8d, eax
0x18002b3c0  jl      short loc_18002B38B
0x18002b3c2  mov     rcx, rsi; void *
0x18002b3c5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b3ca  nop
0x18002b3cb  mov     rcx, [rbp+hDevice]; hObject
0x18002b3cf  lea     rax, [rcx-1]
0x18002b3d3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002b3d7  ja      short loc_18002B3DF
0x18002b3d9  call    cs:__imp_CloseHandle
0x18002b3df  add     rsp, 70h
0x18002b3e3  pop     r15
0x18002b3e5  pop     r14
0x18002b3e7  pop     r12
0x18002b3e9  pop     rdi
0x18002b3ea  pop     rsi
0x18002b3eb  pop     rbx
0x18002b3ec  pop     rbp
0x18002b3ed  retn
0x18002b3ee  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002b3f5  mov     edx, 1Ah; void *
0x18002b3fa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
