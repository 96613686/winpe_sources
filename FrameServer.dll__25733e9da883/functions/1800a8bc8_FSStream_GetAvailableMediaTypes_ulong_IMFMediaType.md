# FSStream::GetAvailableMediaTypes(ulong *,IMFMediaType * * *)

- ea: `0x1800a8bc8`
- end: `0x1800a8cfc`
- name: `?GetAvailableMediaTypes@FSStream@@QEAAJPEAKPEAPEAPEAUIMFMediaType@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(FSStream *__hidden this, unsigned int *, struct IMFMediaType ***)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180095900`

## callees

- `0x180009608`
- `0x1800a8bc8`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a8ce3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a8ce3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a8be6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a8be6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8cd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8cd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a8c60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a8c60`

## pseudocode

```c
__int64 __fastcall FSStream::GetAvailableMediaTypes(FSStream *this, unsigned int *a2, struct IMFMediaType ***a3)
{
  unsigned int v6; // ebp
  __int64 v7; // rdx
  struct IMFMediaType **v8; // r13
  unsigned int v9; // eax
  __int64 i; // r12
  __int64 v11; // rcx
  __int64 v12; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( a2 )
  {
    *a2 = 0;
    if ( a3 )
    {
      *a3 = 0;
      v8 = (struct IMFMediaType **)CoTaskMemAlloc(8LL * *((unsigned int *)this + 30));
      if ( v8 )
      {
        v9 = *((_DWORD *)this + 30);
        v6 = 0;
        for ( i = 0; (unsigned int)i < v9; i = (unsigned int)(i + 1) )
        {
          v11 = *(_QWORD *)(*((_QWORD *)this + 14) + 8 * i);
          v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 320LL))(v11, 2);
          v8[i] = (struct IMFMediaType *)v12;
          if ( v12 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
          v9 = *((_DWORD *)this + 30);
        }
        *a2 = v9;
        *a3 = v8;
      }
      else
      {
        v6 = -2147024882;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids,
            this,
            -2147024882);
      }
    }
    else
    {
      v6 = -2147467261;
      if ( g_wppLevels )
      {
        v7 = 55;
        goto LABEL_4;
      }
    }
  }
  else
  {
    v6 = -2147467261;
    if ( g_wppLevels )
    {
      v7 = 54;
LABEL_4:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids,
        this,
        -2147467261);
    }
  }
  CoTaskMemFree(0);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return v6;
}

```

## disassembly

```asm
0x1800a8bc8  push    rbx
0x1800a8bca  push    rbp
0x1800a8bcb  push    rsi
0x1800a8bcc  push    rdi
0x1800a8bcd  push    r12
0x1800a8bcf  push    r13
0x1800a8bd1  push    r14
0x1800a8bd3  push    r15
0x1800a8bd5  sub     rsp, 38h
0x1800a8bd9  mov     rsi, rcx
0x1800a8bdc  mov     r14, r8
0x1800a8bdf  add     rcx, 18h; lpCriticalSection
0x1800a8be3  mov     r15, rdx
0x1800a8be6  call    cs:__imp_EnterCriticalSection
0x1800a8bec  test    r15, r15
0x1800a8bef  jnz     short loc_1800A8C2C
0x1800a8bf1  mov     eax, 80004003h
0x1800a8bf6  mov     ebp, eax
0x1800a8bf8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a8bff  jb      loc_1800A8CD7
0x1800a8c05  lea     edx, [r15+36h]
0x1800a8c09  mov     [rsp+78h+var_58], eax
0x1800a8c0d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8c14  lea     r8, WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids
0x1800a8c1b  mov     r9, rsi
0x1800a8c1e  mov     rcx, [rcx+10h]
0x1800a8c22  call    WPP_SF_qD
0x1800a8c27  jmp     loc_1800A8CD7
0x1800a8c2c  mov     dword ptr [r15], 0
0x1800a8c33  test    r14, r14
0x1800a8c36  jnz     short loc_1800A8C52
0x1800a8c38  mov     eax, 80004003h
0x1800a8c3d  mov     ebp, eax
0x1800a8c3f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a8c46  jb      loc_1800A8CD7
0x1800a8c4c  lea     edx, [r14+37h]
0x1800a8c50  jmp     short loc_1800A8C09
0x1800a8c52  mov     qword ptr [r14], 0
0x1800a8c59  mov     ecx, [rsi+78h]
0x1800a8c5c  shl     rcx, 3; cb
0x1800a8c60  call    cs:__imp_CoTaskMemAlloc
0x1800a8c66  mov     r13, rax
0x1800a8c69  test    rax, rax
0x1800a8c6c  jnz     short loc_1800A8C85
0x1800a8c6e  mov     ebp, 8007000Eh
0x1800a8c73  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a8c7a  jb      short loc_1800A8CD7
0x1800a8c7c  lea     edx, [rax+38h]
0x1800a8c7f  mov     [rsp+78h+var_58], ebp
0x1800a8c83  jmp     short loc_1800A8C0D
0x1800a8c85  mov     eax, [rsi+78h]
0x1800a8c88  xor     ebp, ebp
0x1800a8c8a  xor     r12d, r12d
0x1800a8c8d  test    eax, eax
0x1800a8c8f  jz      short loc_1800A8CD1
0x1800a8c91  mov     rax, [rsi+70h]
0x1800a8c95  mov     edx, 2
0x1800a8c9a  mov     rcx, [rax+r12*8]
0x1800a8c9e  mov     rax, [rcx]
0x1800a8ca1  mov     rax, [rax+140h]
0x1800a8ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8cad  mov     [r13+r12*8+0], rax
0x1800a8cb2  mov     rcx, rax
0x1800a8cb5  test    rax, rax
0x1800a8cb8  jz      short loc_1800A8CC6
0x1800a8cba  mov     rax, [rax]
0x1800a8cbd  mov     rax, [rax+8]
0x1800a8cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8cc6  mov     eax, [rsi+78h]
0x1800a8cc9  inc     r12d
0x1800a8ccc  cmp     r12d, eax
0x1800a8ccf  jb      short loc_1800A8C91
0x1800a8cd1  mov     [r15], eax
0x1800a8cd4  mov     [r14], r13
0x1800a8cd7  xor     ecx, ecx; pv
0x1800a8cd9  call    cs:__imp_CoTaskMemFree
0x1800a8cdf  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800a8ce3  call    cs:__imp_LeaveCriticalSection
0x1800a8ce9  mov     eax, ebp
0x1800a8ceb  add     rsp, 38h
0x1800a8cef  pop     r15
0x1800a8cf1  pop     r14
0x1800a8cf3  pop     r13
0x1800a8cf5  pop     r12
0x1800a8cf7  pop     rdi
0x1800a8cf8  pop     rsi
0x1800a8cf9  pop     rbp
0x1800a8cfa  pop     rbx
0x1800a8cfb  retn
```
