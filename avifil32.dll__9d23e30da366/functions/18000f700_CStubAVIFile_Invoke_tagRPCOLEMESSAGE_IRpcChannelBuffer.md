# CStubAVIFile::Invoke(tagRPCOLEMESSAGE *,IRpcChannelBuffer *)

- ea: `0x18000f700`
- end: `0x18000fa27`
- name: `?Invoke@CStubAVIFile@@UEAAJPEAUtagRPCOLEMESSAGE@@PEAUIRpcChannelBuffer@@@Z`
- size: `807`
- prototype: `__int64 __fastcall(CStubAVIFile *__hidden this, struct tagRPCOLEMESSAGE *, struct IRpcChannelBuffer *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d0c`
- `0x18000f700`
- `0x180017365`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000f8b0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000f8b0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000f898`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000f898`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000f7ed`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000f7ed`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f8c2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f8c2`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18000f834`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18000f834`
- `api-ms-win-core-com-l1-1-0!CoGetMarshalSizeMax` at `0x18000f7df`
- `api-ms-win-core-com-l1-1-0!CoGetMarshalSizeMax` at `0x18000f7df`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000f805`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000f805`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f9ae`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f9ae`

## pseudocode

```c
__int64 __fastcall CStubAVIFile::Invoke(CStubAVIFile *this, struct tagRPCOLEMESSAGE *a2, struct IRpcChannelBuffer *a3)
{
  __int64 v3; // rsi
  unsigned int *Buffer; // r8
  int v8; // r14d
  HGLOBAL v9; // rax
  void *v10; // rsi
  char *v11; // rbx
  ULONG v12; // edi
  const void *v13; // rax
  int v14; // eax
  int v15; // r14d
  size_t v16; // rsi
  ULONG pulSize; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pvDestContext; // [rsp+48h] [rbp-B8h] BYREF
  LPUNKNOWN pUnk; // [rsp+50h] [rbp-B0h] BYREF
  LPSTREAM ppstm; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDestContext[4]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v22[11]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR WideCharStr[8]; // [rsp+9Ch] [rbp-64h] BYREF
  __int128 v24; // [rsp+ACh] [rbp-54h]
  __int128 v25; // [rsp+BCh] [rbp-44h]
  __int128 v26; // [rsp+CCh] [rbp-34h]
  _DWORD Src[11]; // [rsp+120h] [rbp+20h] BYREF
  CHAR MultiByteStr[64]; // [rsp+14Ch] [rbp+4Ch] BYREF
  int v29; // [rsp+18Ch] [rbp+8Ch]
  __int128 v30; // [rsp+190h] [rbp+90h]
  __int128 v31; // [rsp+1A0h] [rbp+A0h]
  __int128 v32; // [rsp+1B0h] [rbp+B0h]
  __int128 v33; // [rsp+1C0h] [rbp+C0h]

  v3 = *((_QWORD *)this + 2);
  if ( !v3 )
    return 2147614719LL;
  if ( a2->iMethod != 1 )
  {
    if ( a2->iMethod != 2 )
      return 2147614719LL;
    Buffer = (unsigned int *)a2->Buffer;
    pUnk = 0;
    dwDestContext[0] = 0;
    pvDestContext = 0;
    pulSize = 0;
    ppstm = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, LPUNKNOWN *, _QWORD, _QWORD))(*(_QWORD *)v3 + 32LL))(
           v3,
           &pUnk,
           *Buffer,
           Buffer[1]);
    if ( v8 )
    {
      v10 = 0;
    }
    else
    {
      ((void (__fastcall *)(struct IRpcChannelBuffer *, DWORD *, LPVOID *))a3->lpVtbl->GetDestCtx)(
        a3,
        dwDestContext,
        &pvDestContext);
      pulSize = 0;
      CoGetMarshalSizeMax(&pulSize, &IID_IAVIStream, pUnk, dwDestContext[0], pvDestContext, 0);
      v9 = GlobalAlloc(0x42u, pulSize);
      v10 = v9;
      if ( v9 )
      {
        if ( CreateStreamOnHGlobal(v9, 0, &ppstm) >= 0 )
        {
          CoMarshalInterface(ppstm, &IID_IAVIStream, pUnk, dwDestContext[0], pvDestContext, 0);
          ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
        }
LABEL_11:
        a2->cbBuffer = pulSize + 4;
        if ( !((unsigned int (__fastcall *)(struct IRpcChannelBuffer *, struct tagRPCOLEMESSAGE *, GUID *))a3->lpVtbl->GetBuffer)(
                a3,
                a2,
                &IID_IAVIStream) )
        {
          *(_DWORD *)a2->Buffer = v8;
          if ( pulSize )
          {
            v11 = (char *)a2->Buffer;
            v12 = pulSize;
            v13 = GlobalLock(v10);
            memmove_0(v11 + 4, v13, v12);
            GlobalUnlock(v10);
          }
          if ( v10 )
            GlobalFree(v10);
          return 0;
        }
        return 2147549198LL;
      }
    }
    pulSize = 0;
    goto LABEL_11;
  }
  memset_0(v22, 0, 0xACu);
  memset_0(Src, 0, 0xF0u);
  v14 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v3 + 24LL))(v3, v22, 172);
  Src[0] = v22[0];
  v15 = v14;
  Src[1] = v22[1];
  Src[2] = v22[2];
  Src[7] = v22[7];
  Src[3] = v22[3];
  Src[8] = v22[8];
  Src[4] = v22[4];
  Src[9] = v22[9];
  Src[5] = v22[5];
  v30 = *(_OWORD *)WideCharStr;
  Src[10] = v22[10];
  v31 = v24;
  Src[6] = v22[6];
  v32 = v25;
  v33 = v26;
  v29 = 1;
  WideCharToMultiByte(0, 0, WideCharStr, -1, MultiByteStr, 64, 0, 0);
  v16 = *(unsigned int *)a2->Buffer;
  a2->cbBuffer = v16 + 4;
  if ( ((unsigned int (__fastcall *)(struct IRpcChannelBuffer *, struct tagRPCOLEMESSAGE *, GUID *))a3->lpVtbl->GetBuffer)(
         a3,
         a2,
         &IID_IAVIStream) )
  {
    return 2147549198LL;
  }
  *(_DWORD *)a2->Buffer = v15;
  memmove_0((char *)a2->Buffer + 4, Src, v16);
  return 0;
}

```

## disassembly

```asm
0x18000f700  mov     [rsp-8+arg_18], rbx
0x18000f705  push    rbp
0x18000f706  push    rsi
0x18000f707  push    rdi
0x18000f708  push    r14
0x18000f70a  push    r15
0x18000f70c  lea     rbp, [rsp-120h]
0x18000f714  sub     rsp, 220h
0x18000f71b  mov     rax, cs:__security_cookie
0x18000f722  xor     rax, rsp
0x18000f725  mov     [rbp+140h+var_30], rax
0x18000f72c  mov     rsi, [rcx+10h]
0x18000f730  xor     r15d, r15d
0x18000f733  mov     rdi, r8
0x18000f736  mov     rbx, rdx
0x18000f739  test    rsi, rsi
0x18000f73c  jnz     short loc_18000F748
0x18000f73e  mov     eax, 8001FFFFh
0x18000f743  jmp     loc_18000FA01
0x18000f748  mov     ecx, [rdx+1Ch]
0x18000f74b  sub     ecx, 1
0x18000f74e  jz      loc_18000F8CD
0x18000f754  cmp     ecx, 1
0x18000f757  jnz     short loc_18000F73E
0x18000f759  mov     r8, [rdx+10h]
0x18000f75d  mov     rcx, rsi
0x18000f760  mov     [rsp+240h+pUnk], r15
0x18000f765  lea     rdx, [rsp+240h+pUnk]
0x18000f76a  mov     [rsp+240h+dwDestContext], r15d
0x18000f76f  mov     [rsp+240h+var_1F8], r15
0x18000f774  mov     [rsp+240h+pulSize], r15d
0x18000f779  mov     [rsp+240h+ppstm], r15
0x18000f77e  mov     rax, [rsi]
0x18000f781  mov     r9d, [r8+4]
0x18000f785  mov     r8d, [r8]
0x18000f788  mov     rax, [rax+20h]
0x18000f78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f791  mov     r14d, eax
0x18000f794  test    eax, eax
0x18000f796  jnz     loc_18000F84D
0x18000f79c  mov     rcx, [rdi]
0x18000f79f  lea     r8, [rsp+240h+var_1F8]
0x18000f7a4  lea     rdx, [rsp+240h+dwDestContext]
0x18000f7a9  mov     rax, [rcx+30h]
0x18000f7ad  mov     rcx, rdi
0x18000f7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7b5  mov     rax, [rsp+240h+var_1F8]
0x18000f7ba  lea     rdx, IID_IAVIStream; riid
0x18000f7c1  mov     r9d, [rsp+240h+dwDestContext]; dwDestContext
0x18000f7c6  lea     rcx, [rsp+240h+pulSize]; pulSize
0x18000f7cb  mov     r8, [rsp+240h+pUnk]; pUnk
0x18000f7d0  mov     [rsp+240h+mshlflags], r15d; mshlflags
0x18000f7d5  mov     [rsp+240h+pvDestContext], rax; pvDestContext
0x18000f7da  mov     [rsp+240h+pulSize], r15d
0x18000f7df  call    cs:__imp_CoGetMarshalSizeMax
0x18000f7e5  mov     edx, [rsp+240h+pulSize]; dwBytes
0x18000f7e9  lea     ecx, [r14+42h]; uFlags
0x18000f7ed  call    cs:__imp_GlobalAlloc
0x18000f7f3  mov     rsi, rax
0x18000f7f6  test    rax, rax
0x18000f7f9  jz      short loc_18000F850
0x18000f7fb  lea     r8, [rsp+240h+ppstm]; ppstm
0x18000f800  xor     edx, edx; fDeleteOnRelease
0x18000f802  mov     rcx, rax; hGlobal
0x18000f805  call    cs:__imp_CreateStreamOnHGlobal
0x18000f80b  test    eax, eax
0x18000f80d  js      short loc_18000F855
0x18000f80f  mov     rcx, [rsp+240h+var_1F8]
0x18000f814  lea     rdx, IID_IAVIStream; riid
0x18000f81b  mov     r9d, [rsp+240h+dwDestContext]; dwDestContext
0x18000f820  mov     r8, [rsp+240h+pUnk]; pUnk
0x18000f825  mov     [rsp+240h+mshlflags], r15d; mshlflags
0x18000f82a  mov     [rsp+240h+pvDestContext], rcx; pvDestContext
0x18000f82f  mov     rcx, [rsp+240h+ppstm]; pStm
0x18000f834  call    cs:__imp_CoMarshalInterface
0x18000f83a  mov     rcx, [rsp+240h+ppstm]
0x18000f83f  mov     rax, [rcx]
0x18000f842  mov     rax, [rax+10h]
0x18000f846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f84b  jmp     short loc_18000F855
0x18000f84d  mov     rsi, r15
0x18000f850  mov     [rsp+240h+pulSize], r15d
0x18000f855  mov     eax, [rsp+240h+pulSize]
0x18000f859  lea     r8, IID_IAVIStream
0x18000f860  add     eax, 4
0x18000f863  mov     rdx, rbx
0x18000f866  mov     [rbx+18h], eax
0x18000f869  mov     rcx, rdi
0x18000f86c  mov     rax, [rdi]
0x18000f86f  mov     rax, [rax+18h]
0x18000f873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f878  test    eax, eax
0x18000f87a  jnz     loc_18000F9DD
0x18000f880  mov     rax, [rbx+10h]
0x18000f884  mov     [rax], r14d
0x18000f887  mov     eax, [rsp+240h+pulSize]
0x18000f88b  test    eax, eax
0x18000f88d  jz      short loc_18000F8B6
0x18000f88f  mov     rbx, [rbx+10h]
0x18000f893  mov     rcx, rsi; hMem
0x18000f896  mov     edi, eax
0x18000f898  call    cs:__imp_GlobalLock
0x18000f89e  mov     r8d, edi; Size
0x18000f8a1  lea     rcx, [rbx+4]; void *
0x18000f8a5  mov     rdx, rax; Src
0x18000f8a8  call    memmove_0
0x18000f8ad  mov     rcx, rsi; hMem
0x18000f8b0  call    cs:__imp_GlobalUnlock
0x18000f8b6  test    rsi, rsi
0x18000f8b9  jz      loc_18000F9FF
0x18000f8bf  mov     rcx, rsi; hMem
0x18000f8c2  call    cs:__imp_GlobalFree
0x18000f8c8  jmp     loc_18000F9FF
0x18000f8cd  mov     r14d, 0ACh
0x18000f8d3  lea     rcx, [rsp+240h+var_1D0]; void *
0x18000f8d8  mov     r8d, r14d; Size
0x18000f8db  xor     edx, edx; Val
0x18000f8dd  call    memset_0
0x18000f8e2  xor     edx, edx; Val
0x18000f8e4  lea     r8d, [r14+44h]; Size
0x18000f8e8  lea     rcx, [rbp+140h+Src]; void *
0x18000f8ec  call    memset_0
0x18000f8f1  mov     rax, [rsi]
0x18000f8f4  lea     rdx, [rsp+240h+var_1D0]
0x18000f8f9  mov     r8d, r14d
0x18000f8fc  mov     rcx, rsi
0x18000f8ff  mov     rax, [rax+18h]
0x18000f903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f908  mov     ecx, [rsp+240h+var_1D0]
0x18000f90c  lea     r8, [rbp+140h+WideCharStr]; lpWideCharStr
0x18000f910  movups  xmm0, xmmword ptr [rbp+140h+WideCharStr]
0x18000f914  mov     [rbp+140h+Src], ecx
0x18000f917  mov     r14d, eax
0x18000f91a  mov     eax, [rbp+140h+var_1B4]
0x18000f91d  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000f921  mov     ecx, [rsp+240h+var_1CC]
0x18000f925  xor     edx, edx; dwFlags
0x18000f927  movups  xmm1, [rbp+140h+var_194]
0x18000f92b  mov     [rbp+140h+var_11C], ecx
0x18000f92e  mov     ecx, [rsp+240h+var_1C8]
0x18000f932  mov     [rbp+140h+var_118], ecx
0x18000f935  mov     ecx, [rsp+240h+var_1C4]
0x18000f939  mov     [rbp+140h+var_104], eax
0x18000f93c  mov     eax, [rbp+140h+var_1B0]
0x18000f93f  mov     [rbp+140h+var_114], ecx
0x18000f942  mov     ecx, [rbp+140h+var_1C0]
0x18000f945  mov     [rbp+140h+var_100], eax
0x18000f948  mov     eax, [rbp+140h+var_1AC]
0x18000f94b  mov     [rbp+140h+var_110], ecx
0x18000f94e  mov     ecx, [rbp+140h+var_1BC]
0x18000f951  mov     [rbp+140h+var_FC], eax
0x18000f954  mov     eax, [rbp+140h+var_1A8]
0x18000f957  mov     [rbp+140h+var_10C], ecx
0x18000f95a  mov     ecx, [rbp+140h+var_1B8]
0x18000f95d  mov     [rsp+240h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x18000f962  movaps  [rbp+140h+var_B0], xmm0
0x18000f969  movups  xmm0, [rbp+140h+var_184]
0x18000f96d  mov     [rbp+140h+var_F8], eax
0x18000f970  lea     rax, [rbp+140h+MultiByteStr]
0x18000f974  movaps  [rbp+140h+var_A0], xmm1
0x18000f97b  movups  xmm1, [rbp+140h+var_174]
0x18000f97f  mov     [rbp+140h+var_108], ecx
0x18000f982  xor     ecx, ecx; CodePage
0x18000f984  mov     [rsp+240h+lpDefaultChar], r15; lpDefaultChar
0x18000f989  mov     [rsp+240h+mshlflags], 40h ; '@'; cbMultiByte
0x18000f991  movaps  [rbp+140h+var_90], xmm0
0x18000f998  movaps  [rbp+140h+var_80], xmm1
0x18000f99f  mov     [rbp+140h+var_B4], 1
0x18000f9a9  mov     [rsp+240h+pvDestContext], rax; lpMultiByteStr
0x18000f9ae  call    cs:__imp_WideCharToMultiByte
0x18000f9b4  mov     rax, [rbx+10h]
0x18000f9b8  lea     r8, IID_IAVIStream
0x18000f9bf  mov     rdx, rbx
0x18000f9c2  mov     rcx, rdi
0x18000f9c5  mov     esi, [rax]
0x18000f9c7  lea     eax, [rsi+4]
0x18000f9ca  mov     [rbx+18h], eax
0x18000f9cd  mov     rax, [rdi]
0x18000f9d0  mov     rax, [rax+18h]
0x18000f9d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9d9  test    eax, eax
0x18000f9db  jz      short loc_18000F9E4
0x18000f9dd  mov     eax, 8001000Eh
0x18000f9e2  jmp     short loc_18000FA01
0x18000f9e4  mov     rax, [rbx+10h]
0x18000f9e8  lea     rdx, [rbp+140h+Src]; Src
0x18000f9ec  mov     r8, rsi; Size
0x18000f9ef  mov     [rax], r14d
0x18000f9f2  mov     rcx, [rbx+10h]
0x18000f9f6  add     rcx, 4; void *
0x18000f9fa  call    memmove_0
0x18000f9ff  xor     eax, eax
0x18000fa01  mov     rcx, [rbp+140h+var_30]
0x18000fa08  xor     rcx, rsp; StackCookie
0x18000fa0b  call    __security_check_cookie
0x18000fa10  mov     rbx, [rsp+240h+arg_18]
0x18000fa18  add     rsp, 220h
0x18000fa1f  pop     r15
0x18000fa21  pop     r14
0x18000fa23  pop     rdi
0x18000fa24  pop     rsi
0x18000fa25  pop     rbp
0x18000fa26  retn
```
