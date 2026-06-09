# StructuredQuery1::QueryParser::RestateToStringInternal(ICondition *,StructuredQuery1::RESTATEMENT_CONTEXT,int,RESTATEMENT_OPTIONS,wchar_t * *)

- ea: `0x18005a60c`
- end: `0x18005a727`
- name: `?RestateToStringInternal@QueryParser@StructuredQuery1@@AEAAJPEAUICondition@@W4RESTATEMENT_CONTEXT@2@HW4RESTATEMENT_OPTIONS@@PEAPEA_W@Z`
- size: `283`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005bca0`
- `0x1800696c0`
- `0x180069ca0`

## callees

- `0x18002e598`
- `0x18002f3e0`
- `0x18003bed0`
- `0x18005a60c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a6fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a6fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005a6ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005a6ad`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::QueryParser::RestateToStringInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        _QWORD *a6)
{
  void *v6; // rdi
  unsigned int v8; // ebp
  int v10; // ebx
  unsigned __int64 v11; // rsi
  unsigned __int64 v13; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int64 v14; // [rsp+58h] [rbp-50h] BYREF
  SIZE_T cb[9]; // [rsp+60h] [rbp-48h] BYREF

  v6 = 0;
  v8 = a4;
  v13 = -2;
  v10 = StructuredQuery1::QueryParser::RestateInternal(a1, a2, 0, a4, a5, 0, -2, 0, &v13);
  if ( v10 >= 0 )
  {
    v14 = 0;
    v10 = SizeTSub(0xFFFFFFFFFFFFFFFFuLL, v13, &v14);
    if ( v10 >= 0 )
    {
      v11 = v14;
      cb[0] = 0;
      v10 = ULongLongMult(v14, 2u, cb);
      if ( v10 >= 0 )
      {
        v6 = CoTaskMemAlloc(cb[0]);
        if ( v6 )
        {
          v13 = v11;
          v10 = StructuredQuery1::QueryParser::RestateInternal(a1, a2, 0, v8, a5, v6, v11, 0, &v13);
          if ( v10 < 0 )
          {
            CoTaskMemFree(v6);
            v6 = 0;
          }
        }
        else
        {
          v10 = -2147024882;
        }
      }
    }
  }
  *a6 = v6;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18005a60c  mov     r11, rsp
0x18005a60f  push    rbx
0x18005a610  push    rbp
0x18005a611  push    rsi
0x18005a612  push    rdi
0x18005a613  push    r12
0x18005a615  push    r14
0x18005a617  push    r15
0x18005a619  sub     rsp, 70h
0x18005a61d  mov     r12d, [rsp+0A8h+arg_20]
0x18005a625  lea     rax, [r11-58h]
0x18005a629  mov     [r11-68h], rax
0x18005a62d  xor     edi, edi
0x18005a62f  mov     [r11-70h], rdi
0x18005a633  mov     r15, rcx
0x18005a636  xor     r8d, r8d
0x18005a639  mov     ebp, r9d
0x18005a63c  mov     r14, rdx
0x18005a63f  lea     rcx, [rdi-2]
0x18005a643  mov     [r11-78h], rcx
0x18005a647  mov     [r11-58h], rcx
0x18005a64b  mov     rcx, r15
0x18005a64e  mov     [r11-80h], rdi
0x18005a652  mov     [rsp+0A8h+var_88], r12d
0x18005a657  call    ?RestateInternal@QueryParser@StructuredQuery1@@AEAAJPEAUICondition@@W4RESTATEMENT_CONTEXT@2@HW4RESTATEMENT_OPTIONS@@PEA_W_KPEAPEA_WPEA_K@Z; StructuredQuery1::QueryParser::RestateInternal(ICondition *,StructuredQuery1::RESTATEMENT_CONTEXT,int,RESTATEMENT_OPTIONS,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x18005a65c  mov     ebx, eax
0x18005a65e  test    eax, eax
0x18005a660  js      loc_18005A70B
0x18005a666  mov     rdx, [rsp+0A8h+var_58]; unsigned __int64
0x18005a66b  lea     r8, [rsp+0A8h+var_50]; unsigned __int64 *
0x18005a670  or      rcx, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x18005a674  mov     [rsp+0A8h+var_50], rdi
0x18005a679  call    ?SizeTSub@@YAJ_K0PEA_K@Z; SizeTSub(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18005a67e  mov     ebx, eax
0x18005a680  test    eax, eax
0x18005a682  js      loc_18005A70B
0x18005a688  mov     rsi, [rsp+0A8h+var_50]
0x18005a68d  lea     r8, [rsp+0A8h+cb]; unsigned __int64 *
0x18005a692  mov     rcx, rsi; unsigned __int64
0x18005a695  mov     [rsp+0A8h+cb], rdi
0x18005a69a  lea     edx, [rdi+2]; unsigned __int64
0x18005a69d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18005a6a2  mov     ebx, eax
0x18005a6a4  test    eax, eax
0x18005a6a6  js      short loc_18005A70B
0x18005a6a8  mov     rcx, [rsp+0A8h+cb]; cb
0x18005a6ad  call    cs:__imp_CoTaskMemAlloc
0x18005a6b3  mov     rdi, rax
0x18005a6b6  test    rax, rax
0x18005a6b9  jz      short loc_18005A706
0x18005a6bb  lea     rax, [rsp+0A8h+var_58]
0x18005a6c0  mov     [rsp+0A8h+var_58], rsi
0x18005a6c5  mov     [rsp+0A8h+var_68], rax
0x18005a6ca  mov     r9d, ebp
0x18005a6cd  mov     [rsp+0A8h+var_70], 0
0x18005a6d6  xor     r8d, r8d
0x18005a6d9  mov     [rsp+0A8h+var_78], rsi
0x18005a6de  mov     rdx, r14
0x18005a6e1  mov     [rsp+0A8h+var_80], rdi
0x18005a6e6  mov     rcx, r15
0x18005a6e9  mov     [rsp+0A8h+var_88], r12d
0x18005a6ee  call    ?RestateInternal@QueryParser@StructuredQuery1@@AEAAJPEAUICondition@@W4RESTATEMENT_CONTEXT@2@HW4RESTATEMENT_OPTIONS@@PEA_W_KPEAPEA_WPEA_K@Z; StructuredQuery1::QueryParser::RestateInternal(ICondition *,StructuredQuery1::RESTATEMENT_CONTEXT,int,RESTATEMENT_OPTIONS,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x18005a6f3  mov     ebx, eax
0x18005a6f5  test    eax, eax
0x18005a6f7  jns     short loc_18005A70B
0x18005a6f9  mov     rcx, rdi; pv
0x18005a6fc  call    cs:__imp_CoTaskMemFree
0x18005a702  xor     edi, edi
0x18005a704  jmp     short loc_18005A70B
0x18005a706  mov     ebx, 8007000Eh
0x18005a70b  mov     rax, [rsp+0A8h+arg_28]
0x18005a713  mov     [rax], rdi
0x18005a716  mov     eax, ebx
0x18005a718  add     rsp, 70h
0x18005a71c  pop     r15
0x18005a71e  pop     r14
0x18005a720  pop     r12
0x18005a722  pop     rdi
0x18005a723  pop     rsi
0x18005a724  pop     rbp
0x18005a725  pop     rbx
0x18005a726  retn
```
