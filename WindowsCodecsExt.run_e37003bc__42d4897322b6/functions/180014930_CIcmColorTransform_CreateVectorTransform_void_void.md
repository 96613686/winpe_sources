# CIcmColorTransform::CreateVectorTransform(void *,void *)

- ea: `0x180014930`
- end: `0x180014a50`
- name: `?CreateVectorTransform@CIcmColorTransform@@UEAAJPEAX0@Z`
- size: `288`
- prototype: `__int64 __fastcall(CIcmColorTransform *__hidden this, void *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800058c0`
- `0x1800058e0`
- `0x180007410`
- `0x180008240`
- `0x180013ff4`
- `0x180014930`
- `0x1800171c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149d5`

## pseudocode

```c
__int64 __fastcall CIcmColorTransform::CreateVectorTransform(CIcmColorTransform *this, void *a2, void *a3)
{
  int v6; // ebx
  CMTALock *v7; // rbp
  signed int v8; // edi
  unsigned int v9; // edx
  unsigned int v10; // r9d
  void *MultiProfileTransform; // rax
  signed int LastError; // eax
  unsigned int v14; // [rsp+20h] [rbp-58h]
  unsigned int v15; // [rsp+28h] [rbp-50h]
  void *v16[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17; // [rsp+80h] [rbp+8h] BYREF

  LODWORD(v17) = _mm_getcsr();
  v6 = v17;
  if ( (v17 & 0xFF80) != 0x1F80 )
  {
    LODWORD(v17) = 8064;
    _mm_setcsr(0x1F80u);
  }
  v7 = (CIcmColorTransform *)((char *)this - 56);
  v8 = 0;
  CMTALock::Enter((CIcmColorTransform *)((char *)this - 56));
  if ( !a2 || !a3 )
  {
    v8 = -2147024809;
    goto LABEL_13;
  }
  if ( !ICMModule::EnsureLoaded() )
  {
LABEL_14:
    if ( v8 < 0 && g_doStackCaptures )
      DoStackCapture(v8);
    goto LABEL_17;
  }
  v17 = 0;
  v16[0] = a2;
  v16[1] = a3;
  MultiProfileTransform = ICMModule::CreateMultiProfileTransform(v16, v9, (unsigned int *)&v17, v10, v14, v15);
  *((_QWORD *)this + 10) = MultiProfileTransform;
  if ( MultiProfileTransform )
  {
    *((_DWORD *)this + 26) = 1;
    goto LABEL_14;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( v8 < 0 )
  {
LABEL_13:
    CIcmColorTransform::Free((CIcmColorTransform *)((char *)this - 72));
    goto LABEL_14;
  }
LABEL_17:
  if ( v7 )
    CMTALock::Leave(v7);
  if ( (v6 & 0xFF80) != 0x1F80 )
  {
    LODWORD(v17) = v6 & 0xFFFFFFC0;
    _mm_setcsr(v6 & 0xFFFFFFC0);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180014930  push    rbx
0x180014932  push    rbp
0x180014933  push    rsi
0x180014934  push    rdi
0x180014935  push    r14
0x180014937  push    r15
0x180014939  sub     rsp, 48h
0x18001493d  mov     r14, r8
0x180014940  mov     r15, rdx
0x180014943  mov     rsi, rcx
0x180014946  stmxcsr dword ptr [rsp+78h+arg_0]
0x18001494e  mov     ebx, dword ptr [rsp+78h+arg_0]
0x180014955  mov     eax, ebx
0x180014957  and     eax, 0FF80h
0x18001495c  cmp     eax, 1F80h
0x180014961  jz      short loc_180014976
0x180014963  mov     dword ptr [rsp+78h+arg_0], 1F80h
0x18001496e  ldmxcsr dword ptr [rsp+78h+arg_0]
0x180014976  lea     rbp, [rcx-38h]
0x18001497a  xor     edi, edi
0x18001497c  mov     rcx, rbp; this
0x18001497f  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180014984  test    r15, r15
0x180014987  jz      short loc_1800149F0
0x180014989  test    r14, r14
0x18001498c  jz      short loc_1800149F0
0x18001498e  call    ?EnsureLoaded@ICMModule@@SAHXZ; ICMModule::EnsureLoaded(void)
0x180014993  test    eax, eax
0x180014995  jz      short loc_1800149FE
0x180014997  xorps   xmm0, xmm0
0x18001499a  mov     [rsp+78h+arg_0], rdi
0x1800149a2  movups  xmmword ptr [rsp+78h+var_48], xmm0
0x1800149a7  lea     r8, [rsp+78h+arg_0]; unsigned int *
0x1800149af  mov     [rsp+78h+var_48], r15
0x1800149b4  lea     rcx, [rsp+78h+var_48]; void **
0x1800149b9  mov     [rsp+78h+var_48+8], r14
0x1800149be  call    ?CreateMultiProfileTransform@ICMModule@@SAPEAXPEAPEAXKPEAKKKK@Z; ICMModule::CreateMultiProfileTransform(void * *,ulong,ulong *,ulong,ulong,ulong)
0x1800149c3  mov     [rsi+50h], rax
0x1800149c7  test    rax, rax
0x1800149ca  jz      short loc_1800149D5
0x1800149cc  mov     dword ptr [rsi+68h], 1
0x1800149d3  jmp     short loc_1800149FE
0x1800149d5  call    cs:__imp_GetLastError
0x1800149db  mov     edi, eax
0x1800149dd  test    eax, eax
0x1800149df  jle     short loc_1800149EA
0x1800149e1  movzx   edi, ax
0x1800149e4  or      edi, 80070000h
0x1800149ea  test    edi, edi
0x1800149ec  js      short loc_1800149F5
0x1800149ee  jmp     short loc_180014A12
0x1800149f0  mov     edi, 80070057h
0x1800149f5  lea     rcx, [rsi-48h]; this
0x1800149f9  call    ?Free@CIcmColorTransform@@IEAAXXZ; CIcmColorTransform::Free(void)
0x1800149fe  test    edi, edi
0x180014a00  jns     short loc_180014A12
0x180014a02  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180014a09  jz      short loc_180014A12
0x180014a0b  mov     ecx, edi; int
0x180014a0d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180014a12  test    rbp, rbp
0x180014a15  jz      short loc_180014A1F
0x180014a17  mov     rcx, rbp; this
0x180014a1a  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x180014a1f  mov     ecx, ebx
0x180014a21  and     ecx, 0FF80h
0x180014a27  cmp     ecx, 1F80h
0x180014a2d  jz      short loc_180014A41
0x180014a2f  and     ebx, 0FFFFFFC0h
0x180014a32  mov     dword ptr [rsp+78h+arg_0], ebx
0x180014a39  ldmxcsr dword ptr [rsp+78h+arg_0]
0x180014a41  mov     eax, edi
0x180014a43  add     rsp, 48h
0x180014a47  pop     r15
0x180014a49  pop     r14
0x180014a4b  pop     rdi
0x180014a4c  pop     rsi
0x180014a4d  pop     rbp
0x180014a4e  pop     rbx
0x180014a4f  retn
```
