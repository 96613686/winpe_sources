# CStandardCollectorService::MarshallCollectorService(std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x140008434`
- end: `0x1400086fa`
- name: `?MarshallCollectorService@CStandardCollectorService@@AEAAJAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `710`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140009030`

## callees

- `0x140008434`
- `0x140008ef4`
- `0x1400137e0`
- `0x14001473e`
- `0x140014bc0`
- `0x140014c70`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1400086ce`
- `KERNEL32!GlobalFree` at `0x140008475`
- `KERNEL32!GlobalFree` at `0x1400086ce`
- `KERNEL32!GlobalAlloc` at `0x14000846c`
- `KERNEL32!GlobalAlloc` at `0x14000846c`
- `KERNEL32!GlobalLock` at `0x1400085a1`
- `KERNEL32!GlobalLock` at `0x1400085a1`
- `KERNEL32!GlobalUnlock` at `0x140008660`
- `KERNEL32!GlobalUnlock` at `0x140008686`
- `KERNEL32!GlobalUnlock` at `0x140008660`
- `KERNEL32!GlobalUnlock` at `0x140008686`
- `KERNEL32!GetLastError` at `0x140008489`
- `KERNEL32!GetLastError` at `0x1400085af`
- `KERNEL32!GetLastError` at `0x140008489`
- `KERNEL32!GetLastError` at `0x1400085af`
- `ole32!CreateStreamOnHGlobal` at `0x1400084b3`
- `ole32!CreateStreamOnHGlobal` at `0x1400084b3`
- `ole32!CoMarshalInterface` at `0x140008519`
- `ole32!CoMarshalInterface` at `0x140008519`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000863c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140008671`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000863c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140008671`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000867d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000867d`

## pseudocode

```c
__int64 __fastcall CStandardCollectorService::MarshallCollectorService(__int64 a1, void **a2)
{
  HGLOBAL v4; // rax
  void *v5; // rsi
  signed int LastError; // eax
  int v7; // ebx
  const void *v8; // r15
  signed int v9; // eax
  char *v10; // r14
  char *v11; // rcx
  char *v12; // rax
  size_t v13; // rbx
  void *v14; // rcx
  size_t v15; // r8
  LPSTREAM ppstm; // [rsp+48h] [rbp-41h] BYREF
  LPUNKNOWN pUnk[2]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v19[16]; // [rsp+60h] [rbp-29h] BYREF
  unsigned int Size; // [rsp+70h] [rbp-19h]
  int Size_4; // [rsp+74h] [rbp-15h]

  v4 = GlobalAlloc(2u, 0);
  v5 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    v7 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v7 = LastError;
    goto LABEL_38;
  }
  ppstm = 0;
  v7 = CreateStreamOnHGlobal(v4, 0, &ppstm);
  if ( v7 >= 0 )
  {
    pUnk[0] = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, LPUNKNOWN *))(**(_QWORD **)(a1 + 64) + 24LL))(
           *(_QWORD *)(a1 + 64),
           0,
           &GUID_7ae366c7_e696_4178_98d0_dd8d48cd5e44,
           pUnk);
    if ( v7 >= 0 )
    {
      v7 = CoMarshalInterface(ppstm, &GUID_7ae366c7_e696_4178_98d0_dd8d48cd5e44, pUnk[0], 1u, 0, 1u);
      if ( v7 >= 0 )
      {
        v7 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
        if ( v7 >= 0 )
        {
          memset_0(v19, 0, 0x50u);
          v7 = ((__int64 (__fastcall *)(LPSTREAM, _BYTE *, __int64))ppstm->lpVtbl->Stat)(ppstm, v19, 1);
          if ( v7 >= 0 )
          {
            if ( !Size_4 && Size )
            {
              _mm_lfence();
              v8 = GlobalLock(v5);
              if ( !v8 )
              {
                v9 = GetLastError();
                v7 = (unsigned __int16)v9 | 0x80070000;
                if ( v9 <= 0 )
                  v7 = v9;
                goto LABEL_34;
              }
              v10 = (char *)a2[1];
              v11 = (char *)*a2;
              if ( *a2 != v10 )
              {
                a2[1] = v11;
                v10 = v11;
              }
              if ( Size >= (unsigned __int64)(v10 - v11) )
              {
                if ( Size <= (unsigned __int64)(v10 - v11) )
                  goto LABEL_25;
                if ( Size > (unsigned __int64)((_BYTE *)a2[2] - v11) )
                {
                  _mm_lfence();
                  std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a2, Size);
                  goto LABEL_25;
                }
                v13 = Size - (v10 - v11);
                memset_0(v10, 0, v13);
                v12 = &v10[v13];
              }
              else
              {
                v12 = &v11[Size];
              }
              a2[1] = v12;
LABEL_25:
              v14 = *a2;
              v15 = (_BYTE *)a2[1] - (_BYTE *)*a2;
              if ( Size )
              {
                if ( !v14 )
                {
                  *_errno() = 22;
LABEL_32:
                  _invalid_parameter_noinfo();
                  GlobalUnlock(v5);
                  v7 = -2147024888;
                  goto LABEL_34;
                }
                if ( v15 < Size )
                {
                  memset_0(v14, 0, v15);
                  *_errno() = 34;
                  goto LABEL_32;
                }
                _mm_lfence();
                memcpy_0(v14, v8, Size);
              }
              GlobalUnlock(v5);
              v7 = 0;
              goto LABEL_34;
            }
            v7 = -2147018183;
          }
        }
      }
    }
LABEL_34:
    if ( pUnk[0] )
      ((void (__fastcall *)(LPUNKNOWN))pUnk[0]->lpVtbl->Release)(pUnk[0]);
  }
  if ( ppstm )
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
LABEL_38:
  if ( v5 )
    GlobalFree(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140008434  mov     [rsp-8+arg_10], rbx
0x140008439  push    rbp
0x14000843a  push    rsi
0x14000843b  push    rdi
0x14000843c  push    r14
0x14000843e  push    r15
0x140008440  lea     rbp, [rsp-37h]
0x140008445  sub     rsp, 0C0h
0x14000844c  mov     rax, cs:__security_cookie
0x140008453  xor     rax, rsp
0x140008456  mov     [rbp+57h+var_30], rax
0x14000845a  mov     rdi, rdx
0x14000845d  mov     r14, rcx
0x140008460  xorps   xmm0, xmm0
0x140008463  movups  [rbp+57h+var_A8], xmm0
0x140008467  xor     edx, edx; dwBytes
0x140008469  lea     ecx, [rdx+2]; uFlags
0x14000846c  call    cs:__imp_GlobalAlloc
0x140008472  mov     rsi, rax
0x140008475  mov     rdx, cs:__imp_GlobalFree
0x14000847c  mov     qword ptr [rbp+57h+var_A8], rdx
0x140008480  mov     qword ptr [rbp+57h+var_A8+8], rax
0x140008484  test    rax, rax
0x140008487  jnz     short loc_1400084A2
0x140008489  call    cs:__imp_GetLastError
0x14000848f  movzx   ebx, ax
0x140008492  or      ebx, 80070000h
0x140008498  test    eax, eax
0x14000849a  cmovle  ebx, eax
0x14000849d  jmp     loc_1400086C6
0x1400084a2  mov     [rbp+57h+ppstm], 0
0x1400084aa  lea     r8, [rbp+57h+ppstm]; ppstm
0x1400084ae  xor     edx, edx; fDeleteOnRelease
0x1400084b0  mov     rcx, rsi; hGlobal
0x1400084b3  call    cs:__imp_CreateStreamOnHGlobal
0x1400084b9  mov     ebx, eax
0x1400084bb  test    eax, eax
0x1400084bd  js      loc_1400086AF
0x1400084c3  mov     [rbp+57h+pUnk], 0
0x1400084cb  mov     rcx, [r14+40h]
0x1400084cf  mov     rax, [rcx]
0x1400084d2  lea     r9, [rbp+57h+pUnk]
0x1400084d6  lea     r8, _GUID_7ae366c7_e696_4178_98d0_dd8d48cd5e44
0x1400084dd  xor     edx, edx
0x1400084df  mov     rax, [rax+18h]
0x1400084e3  call    cs:__guard_dispatch_icall_fptr
0x1400084e9  mov     ebx, eax
0x1400084eb  test    eax, eax
0x1400084ed  js      loc_140008698
0x1400084f3  mov     r14d, 1
0x1400084f9  mov     [rsp+0E0h+mshlflags], r14d; mshlflags
0x1400084fe  mov     [rsp+0E0h+pvDestContext], 0; pvDestContext
0x140008507  mov     r9d, r14d; dwDestContext
0x14000850a  mov     r8, [rbp+57h+pUnk]; pUnk
0x14000850e  lea     rdx, _GUID_7ae366c7_e696_4178_98d0_dd8d48cd5e44; riid
0x140008515  mov     rcx, [rbp+57h+ppstm]; pStm
0x140008519  call    cs:__imp_CoMarshalInterface
0x14000851f  mov     ebx, eax
0x140008521  test    eax, eax
0x140008523  js      loc_140008698
0x140008529  mov     [rbp+57h+var_B0], 0
0x140008531  mov     rcx, [rbp+57h+ppstm]
0x140008535  mov     rax, [rcx]
0x140008538  xor     r9d, r9d
0x14000853b  xor     r8d, r8d
0x14000853e  mov     rdx, [rbp+57h+var_B0]
0x140008542  mov     rax, [rax+28h]
0x140008546  call    cs:__guard_dispatch_icall_fptr
0x14000854c  mov     ebx, eax
0x14000854e  test    eax, eax
0x140008550  js      loc_140008698
0x140008556  xor     edx, edx; Val
0x140008558  lea     r8d, [r14+4Fh]; Size
0x14000855c  lea     rcx, [rbp+57h+var_80]; void *
0x140008560  call    memset_0
0x140008565  mov     rcx, [rbp+57h+ppstm]
0x140008569  mov     rax, [rcx]
0x14000856c  mov     r8d, r14d
0x14000856f  lea     rdx, [rbp+57h+var_80]
0x140008573  mov     rax, [rax+60h]
0x140008577  call    cs:__guard_dispatch_icall_fptr
0x14000857d  mov     ebx, eax
0x14000857f  test    eax, eax
0x140008581  js      loc_140008698
0x140008587  cmp     dword ptr [rbp+57h+Size+4], 0
0x14000858b  jnz     loc_140008693
0x140008591  cmp     dword ptr [rbp+57h+Size], 0
0x140008595  jz      loc_140008693
0x14000859b  lfence
0x14000859e  mov     rcx, rsi; hMem
0x1400085a1  call    cs:__imp_GlobalLock
0x1400085a7  mov     r15, rax
0x1400085aa  test    rax, rax
0x1400085ad  jnz     short loc_1400085C8
0x1400085af  call    cs:__imp_GetLastError
0x1400085b5  movzx   ebx, ax
0x1400085b8  or      ebx, 80070000h
0x1400085be  test    eax, eax
0x1400085c0  cmovle  ebx, eax
0x1400085c3  jmp     loc_140008698
0x1400085c8  mov     r14, [rdi+8]
0x1400085cc  mov     rcx, [rdi]
0x1400085cf  cmp     rcx, r14
0x1400085d2  jz      short loc_1400085DB
0x1400085d4  mov     [rdi+8], rcx
0x1400085d8  mov     r14, rcx
0x1400085db  mov     ebx, dword ptr [rbp+57h+Size]
0x1400085de  mov     rdx, r14
0x1400085e1  sub     rdx, rcx
0x1400085e4  cmp     rbx, rdx
0x1400085e7  jnb     short loc_1400085EF
0x1400085e9  lea     rax, [rcx+rbx]
0x1400085ed  jmp     short loc_140008621
0x1400085ef  jbe     short loc_140008625
0x1400085f1  mov     rax, [rdi+10h]
0x1400085f5  sub     rax, rcx
0x1400085f8  cmp     rbx, rax
0x1400085fb  jbe     short loc_14000860D
0x1400085fd  lfence
0x140008600  mov     rdx, rbx
0x140008603  mov     rcx, rdi
0x140008606  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x14000860b  jmp     short loc_140008625
0x14000860d  sub     rbx, rdx
0x140008610  mov     r8, rbx; Size
0x140008613  xor     edx, edx; Val
0x140008615  mov     rcx, r14; void *
0x140008618  call    memset_0
0x14000861d  lea     rax, [r14+rbx]
0x140008621  mov     [rdi+8], rax
0x140008625  mov     rcx, [rdi]; void *
0x140008628  mov     r8, [rdi+8]
0x14000862c  sub     r8, rcx; Size
0x14000862f  mov     eax, dword ptr [rbp+57h+Size]
0x140008632  test    rax, rax
0x140008635  jz      short loc_14000865D
0x140008637  test    rcx, rcx
0x14000863a  jnz     short loc_14000864A
0x14000863c  call    cs:__imp__errno
0x140008642  mov     dword ptr [rax], 16h
0x140008648  jmp     short loc_14000867D
0x14000864a  cmp     r8, rax
0x14000864d  jb      short loc_14000866A
0x14000864f  lfence
0x140008652  mov     r8, rax; Size
0x140008655  mov     rdx, r15; Src
0x140008658  call    memcpy_0
0x14000865d  mov     rcx, rsi; hMem
0x140008660  call    cs:__imp_GlobalUnlock
0x140008666  xor     ebx, ebx
0x140008668  jmp     short loc_140008698
0x14000866a  xor     edx, edx; Val
0x14000866c  call    memset_0
0x140008671  call    cs:__imp__errno
0x140008677  mov     dword ptr [rax], 22h ; '"'
0x14000867d  call    cs:__imp__invalid_parameter_noinfo
0x140008683  mov     rcx, rsi; hMem
0x140008686  call    cs:__imp_GlobalUnlock
0x14000868c  mov     ebx, 80070008h
0x140008691  jmp     short loc_140008698
0x140008693  mov     ebx, 80071A39h
0x140008698  mov     rcx, [rbp+57h+pUnk]
0x14000869c  test    rcx, rcx
0x14000869f  jz      short loc_1400086AF
0x1400086a1  mov     rax, [rcx]
0x1400086a4  mov     rax, [rax+10h]
0x1400086a8  call    cs:__guard_dispatch_icall_fptr
0x1400086ae  nop
0x1400086af  mov     rcx, [rbp+57h+ppstm]
0x1400086b3  test    rcx, rcx
0x1400086b6  jz      short loc_1400086C6
0x1400086b8  mov     rax, [rcx]
0x1400086bb  mov     rax, [rax+10h]
0x1400086bf  call    cs:__guard_dispatch_icall_fptr
0x1400086c5  nop
0x1400086c6  test    rsi, rsi
0x1400086c9  jz      short loc_1400086D5
0x1400086cb  mov     rcx, rsi; hMem
0x1400086ce  call    cs:__imp_GlobalFree
0x1400086d4  nop
0x1400086d5  mov     eax, ebx
0x1400086d7  mov     rcx, [rbp+57h+var_30]
0x1400086db  xor     rcx, rsp; StackCookie
0x1400086de  call    __security_check_cookie
0x1400086e3  mov     rbx, [rsp+0E0h+arg_10]
0x1400086eb  add     rsp, 0C0h
0x1400086f2  pop     r15
0x1400086f4  pop     r14
0x1400086f6  pop     rdi
0x1400086f7  pop     rsi
0x1400086f8  pop     rbp
0x1400086f9  retn
```
