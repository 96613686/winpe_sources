# XvmmPort::StartXboxProxy(uchar,uchar,unsigned __int64,uint *)

- ea: `0x18002b60c`
- end: `0x18002b7a4`
- name: `?StartXboxProxy@XvmmPort@@AEAAJEE_KPEAI@Z`
- size: `408`
- prototype: `__int64 __fastcall(XvmmPort *__hidden this, unsigned __int8, unsigned __int8, unsigned __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002774c`

## callees

- `0x180025234`
- `0x180029c1c`
- `0x18002b60c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b683`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b683`

## pseudocode

```c
__int64 __fastcall XvmmPort::StartXboxProxy(XvmmPort *this, char a2, char a3, __int64 a4, unsigned int *a5)
{
  unsigned int *v5; // rdi
  int v10; // ebx
  HRESULT v11; // eax
  LPVOID v12; // rcx
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  __int128 v17; // xmm0
  __int64 (__fastcall *v18)(__int64, __int128 *, __int64, __int64, int, __int64, unsigned int **); // rax
  int v19; // eax
  int ppv; // [rsp+20h] [rbp-61h]
  LPVOID v22; // [rsp+40h] [rbp-41h] BYREF
  __int64 v23; // [rsp+48h] [rbp-39h] BYREF
  __int128 v24; // [rsp+50h] [rbp-31h] BYREF
  _QWORD v25[4]; // [rsp+60h] [rbp-21h] BYREF
  char v26; // [rsp+80h] [rbp-1h]

  v5 = a5;
  memset(v25, 0, 24);
  *a5 = 0;
  v25[3] = 0;
  v26 = 0;
  v10 = XboxMTAUsageWrapper::Initialize((XboxMTAUsageWrapper *)v25);
  if ( v10 >= 0 )
  {
    v22 = 0;
    v11 = CoCreateInstance(
            &GUID_f5715449_10f6_4225_a7c6_d584bd3c7f5b,
            0,
            0x17u,
            &GUID_9a57863e_b229_4696_a8d4_40e5eb792d0f,
            &v22);
    v12 = v22;
    v10 = v11;
    if ( v11 >= 0 )
    {
      v23 = 0;
      v13 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v22)(
              v22,
              &GUID_af7f45cf_0c68_46de_afed_252bbff0c9c4,
              &v23);
      v16 = v23;
      v10 = v13;
      if ( v13 < 0 )
        goto LABEL_6;
      v17 = *((_OWORD *)this + 4);
      LODWORD(a5) = 0;
      LOBYTE(v15) = a3;
      LOBYTE(v14) = a2;
      v18 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64, __int64, int, __int64, unsigned int **))(*(_QWORD *)v23 + 24LL);
      LOWORD(ppv) = *((_WORD *)this + 40);
      v24 = v17;
      v19 = v18(v23, &v24, v14, v15, ppv, a4, &a5);
      v16 = v23;
      v10 = v19;
      if ( v19 < 0 )
      {
LABEL_6:
        if ( v16 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          v23 = 0;
        }
        v12 = v22;
        if ( v22 )
          goto LABEL_4;
      }
      else
      {
        *v5 = (unsigned int)a5;
        *((_BYTE *)this + 82) = 1;
        if ( v16 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          v23 = 0;
        }
        if ( v22 )
        {
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
          v22 = 0;
        }
        v10 = 0;
      }
    }
    else if ( v22 )
    {
LABEL_4:
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v12);
      v22 = 0;
    }
  }
  XboxMTAUsageWrapper::~XboxMTAUsageWrapper((XboxMTAUsageWrapper *)v25);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002b60c  push    rbp
0x18002b60e  push    rbx
0x18002b60f  push    rsi
0x18002b610  push    rdi
0x18002b611  push    r12
0x18002b613  push    r13
0x18002b615  push    r14
0x18002b617  push    r15
0x18002b619  lea     rbp, [rsp-17h]
0x18002b61e  sub     rsp, 98h
0x18002b625  mov     rdi, [rbp+4Fh+arg_20]
0x18002b629  xor     r13d, r13d
0x18002b62c  mov     rsi, rcx
0x18002b62f  mov     [rbp+4Fh+var_70], r13
0x18002b633  lea     rcx, [rbp+4Fh+var_70]; this
0x18002b637  mov     [rbp+4Fh+var_68], r13
0x18002b63b  mov     r14, r9
0x18002b63e  mov     [rbp+4Fh+var_60], r13
0x18002b642  mov     [rdi], r13d
0x18002b645  mov     r15b, r8b
0x18002b648  mov     r12b, dl
0x18002b64b  mov     [rbp+4Fh+var_58], r13
0x18002b64f  mov     [rbp+4Fh+var_50], r13b
0x18002b653  call    ?Initialize@XboxMTAUsageWrapper@@QEAAJXZ; XboxMTAUsageWrapper::Initialize(void)
0x18002b658  mov     ebx, eax
0x18002b65a  test    eax, eax
0x18002b65c  js      loc_18002B784
0x18002b662  lea     rax, [rbp+4Fh+var_90]
0x18002b666  mov     [rbp+4Fh+var_90], r13
0x18002b66a  lea     r9, _GUID_9a57863e_b229_4696_a8d4_40e5eb792d0f; riid
0x18002b671  mov     [rsp+0D0h+ppv], rax; ppv
0x18002b676  xor     edx, edx; pUnkOuter
0x18002b678  lea     r8d, [r13+17h]; dwClsContext
0x18002b67c  lea     rcx, _GUID_f5715449_10f6_4225_a7c6_d584bd3c7f5b; rclsid
0x18002b683  call    cs:__imp_CoCreateInstance
0x18002b68a  nop     dword ptr [rax+rax+00h]
0x18002b68f  mov     rcx, [rbp+4Fh+var_90]
0x18002b693  mov     ebx, eax
0x18002b695  test    eax, eax
0x18002b697  jns     short loc_18002B6B7
0x18002b699  test    rcx, rcx
0x18002b69c  jz      loc_18002B784
0x18002b6a2  mov     rdx, [rcx]
0x18002b6a5  mov     rax, [rdx+10h]
0x18002b6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6ae  mov     [rbp+4Fh+var_90], r13
0x18002b6b2  jmp     loc_18002B784
0x18002b6b7  mov     [rbp+4Fh+var_88], r13
0x18002b6bb  lea     r8, [rbp+4Fh+var_88]
0x18002b6bf  mov     rax, [rcx]
0x18002b6c2  lea     rdx, _GUID_af7f45cf_0c68_46de_afed_252bbff0c9c4
0x18002b6c9  mov     rax, [rax]
0x18002b6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6d1  mov     rcx, [rbp+4Fh+var_88]
0x18002b6d5  mov     ebx, eax
0x18002b6d7  test    eax, eax
0x18002b6d9  jns     short loc_18002B706
0x18002b6db  test    rcx, rcx
0x18002b6de  jz      short loc_18002B6F0
0x18002b6e0  mov     rdx, [rcx]
0x18002b6e3  mov     rax, [rdx+10h]
0x18002b6e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6ec  mov     [rbp+4Fh+var_88], r13
0x18002b6f0  mov     rcx, [rbp+4Fh+var_90]
0x18002b6f4  test    rcx, rcx
0x18002b6f7  jz      loc_18002B784
0x18002b6fd  mov     rax, [rcx]
0x18002b700  mov     rax, [rax+10h]
0x18002b704  jmp     short loc_18002B6A9
0x18002b706  movups  xmm0, xmmword ptr [rsi+40h]
0x18002b70a  lea     rdx, [rbp+4Fh+arg_20]
0x18002b70e  mov     dword ptr [rbp+4Fh+arg_20], r13d
0x18002b712  mov     rax, [rcx]
0x18002b715  mov     r9b, r15b
0x18002b718  mov     [rsp+0D0h+var_A0], rdx
0x18002b71d  mov     r8b, r12b
0x18002b720  movzx   edx, word ptr [rsi+50h]
0x18002b724  mov     [rsp+0D0h+var_A8], r14
0x18002b729  mov     rax, [rax+18h]
0x18002b72d  mov     word ptr [rsp+0D0h+ppv], dx
0x18002b732  lea     rdx, [rbp+4Fh+var_80]
0x18002b736  movdqu  [rbp+4Fh+var_80], xmm0
0x18002b73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b740  mov     rcx, [rbp+4Fh+var_88]
0x18002b744  mov     ebx, eax
0x18002b746  test    eax, eax
0x18002b748  js      short loc_18002B6DB
0x18002b74a  mov     eax, dword ptr [rbp+4Fh+arg_20]
0x18002b74d  mov     [rdi], eax
0x18002b74f  mov     byte ptr [rsi+52h], 1
0x18002b753  test    rcx, rcx
0x18002b756  jz      short loc_18002B768
0x18002b758  mov     rax, [rcx]
0x18002b75b  mov     rax, [rax+10h]
0x18002b75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b764  mov     [rbp+4Fh+var_88], r13
0x18002b768  mov     rcx, [rbp+4Fh+var_90]
0x18002b76c  test    rcx, rcx
0x18002b76f  jz      short loc_18002B781
0x18002b771  mov     rax, [rcx]
0x18002b774  mov     rax, [rax+10h]
0x18002b778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b77d  mov     [rbp+4Fh+var_90], r13
0x18002b781  mov     ebx, r13d
0x18002b784  lea     rcx, [rbp+4Fh+var_70]; this
0x18002b788  call    ??1XboxMTAUsageWrapper@@QEAA@XZ; XboxMTAUsageWrapper::~XboxMTAUsageWrapper(void)
0x18002b78d  mov     eax, ebx
0x18002b78f  add     rsp, 98h
0x18002b796  pop     r15
0x18002b798  pop     r14
0x18002b79a  pop     r13
0x18002b79c  pop     r12
0x18002b79e  pop     rdi
0x18002b79f  pop     rsi
0x18002b7a0  pop     rbx
0x18002b7a1  pop     rbp
0x18002b7a2  retn
```
