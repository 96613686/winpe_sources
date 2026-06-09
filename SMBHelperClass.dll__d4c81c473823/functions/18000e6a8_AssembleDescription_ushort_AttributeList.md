# AssembleDescription(ushort *,AttributeList *)

- ea: `0x18000e6a8`
- end: `0x18000ea1b`
- name: `?AssembleDescription@@YAPEAGPEAGPEAVAttributeList@@@Z`
- size: `883`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *, struct AttributeList *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800067d0`
- `0x18000fa20`

## callees

- `0x18000257c`
- `0x18000a25c`
- `0x18000a320`
- `0x18000dd04`
- `0x18000e6a8`
- `0x18000ea24`
- `0x18000eddc`
- `0x18000ee10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e7fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e877`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e8aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e7fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e877`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e8aa`

## pseudocode

```c
unsigned __int16 *__fastcall AssembleDescription(unsigned __int16 *a1, struct AttributeList *a2)
{
  struct AttributeList *v2; // r12
  char *TestMemory; // rax
  char *v5; // rdi
  __int64 v6; // r15
  unsigned __int64 v7; // rsi
  unsigned __int16 *v8; // rbx
  int v9; // eax
  unsigned __int16 *v10; // r13
  __int64 v11; // r14
  unsigned __int16 *v12; // r8
  unsigned __int16 *v13; // r12
  unsigned __int64 v14; // r11
  __int64 v15; // rax
  unsigned __int16 *v16; // rbx
  unsigned __int16 *result; // rax
  int pExceptionObject; // [rsp+20h] [rbp-88h] BYREF
  int v19; // [rsp+24h] [rbp-84h] BYREF
  int v20; // [rsp+28h] [rbp-80h] BYREF
  int v21; // [rsp+2Ch] [rbp-7Ch] BYREF
  int v22; // [rsp+30h] [rbp-78h] BYREF
  int v23; // [rsp+34h] [rbp-74h] BYREF
  int v24; // [rsp+38h] [rbp-70h] BYREF
  int v25; // [rsp+3Ch] [rbp-6Ch] BYREF
  int v26; // [rsp+40h] [rbp-68h] BYREF
  int v27; // [rsp+44h] [rbp-64h] BYREF
  int v28; // [rsp+48h] [rbp-60h] BYREF
  int v29; // [rsp+4Ch] [rbp-5Ch] BYREF
  int v30; // [rsp+50h] [rbp-58h] BYREF
  int v31; // [rsp+54h] [rbp-54h] BYREF
  _BYTE v32[80]; // [rsp+58h] [rbp-50h] BYREF
  unsigned __int16 *v33; // [rsp+B0h] [rbp+8h]
  char *v35; // [rsp+C0h] [rbp+18h]
  unsigned __int16 *v36; // [rsp+C8h] [rbp+20h]

  v2 = a2;
  if ( !a1 || !a2 )
  {
    v28 = 4;
    throw (TestException *)&v28;
  }
  TestMemory = (char *)AllocateTestMemory(0x800u);
  v5 = TestMemory;
  v35 = TestMemory;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  try
  {
    *(_WORD *)TestMemory = 0;
    v8 = (unsigned __int16 *)AllocateTestMemory(2 * v7 + 2);
    v36 = v8;
    v9 = StringCchCopyW(v8, v7 + 1, a1);
  }
  catch ( TestException v31 )
  {
    FreeTestMemory(v35);
    v27 = v31;
    throw (TestException *)&v27;
  }
  if ( v9 )
  {
    FreeTestMemory(v8);
    FreeTestMemory(v5);
    pExceptionObject = 4;
    throw (TestException *)&pExceptionObject;
  }
  v10 = (unsigned __int16 *)v5;
  v33 = v8;
  LODWORD(v11) = 0;
  while ( (unsigned int)v11 < v7 )
  {
    if ( v8[(unsigned int)v11] == 37 )
    {
      v8[(unsigned int)v11] = 0;
      v11 = (unsigned int)(v11 + 1);
      v12 = &v8[v11];
      if ( *v12 != 37 )
      {
        do
        {
          if ( (unsigned int)v11 >= v7 )
            break;
          v11 = (unsigned int)(v11 + 1);
        }
        while ( v8[v11] != 37 );
      }
      if ( (unsigned int)v11 >= v7 )
      {
        FreeTestMemory(v8);
        FreeTestMemory(v5);
        v19 = 4;
        throw (TestException *)&v19;
      }
      try
      {
        v8[v11] = 0;
        AttributeList::getAttribute(v2, v32, v12, 3);
        v13 = ConvertAttributeValueToString((const struct Attribute *)v32);
      }
      catch ( TestException v29 )
      {
        FreeTestMemory(v36);
        FreeTestMemory(v35);
        v23 = v29;
        throw (TestException *)&v23;
      }
      if ( v10 >= (unsigned __int16 *)v5 + 1024 )
      {
        FreeTestMemory(v8);
        FreeTestMemory(v5);
        FreeTestMemory(v13);
        v20 = 4;
        throw (TestException *)&v20;
      }
      if ( (unsigned int)StringCchCopyW(v10, (v5 + 2048 - (char *)v10) >> 1, v33) )
      {
        FreeTestMemory(v8);
        FreeTestMemory(v5);
        FreeTestMemory(v13);
        v21 = 4;
        throw (TestException *)&v21;
      }
      if ( (unsigned int)StringCchCatW(v10, v14, v13) )
      {
        FreeTestMemory(v8);
        FreeTestMemory(v5);
        FreeTestMemory(v13);
        v22 = 4;
        throw (TestException *)&v22;
      }
      CoTaskMemFree(v13);
      v33 = &v8[(unsigned int)(v11 + 1)];
      v15 = -1;
      do
        ++v15;
      while ( v10[v15] );
      v10 += v15;
      v2 = a2;
    }
    LODWORD(v11) = v11 + 1;
  }
  if ( v33 < &v8[v7] )
  {
    if ( v10 >= (unsigned __int16 *)v5 + 1024 )
    {
      FreeTestMemory(v8);
      FreeTestMemory(v5);
      v24 = 4;
      throw (TestException *)&v24;
    }
    if ( (unsigned int)StringCchCatW((unsigned __int16 *)v5, 0x400u, v33) )
    {
      FreeTestMemory(v8);
      FreeTestMemory(v5);
      v25 = 4;
      throw (TestException *)&v25;
    }
  }
  CoTaskMemFree(v8);
  do
    ++v6;
  while ( *(_WORD *)&v5[2 * v6] );
  try
  {
    v16 = (unsigned __int16 *)AllocateTestMemory(2 * v6 + 2);
    StringCchCopyW(v16, v6 + 1, (const unsigned __int16 *)v5);
    CoTaskMemFree(v5);
    result = v16;
  }
  catch ( TestException v30 )
  {
    FreeTestMemory(v35);
    v26 = v30;
    throw (TestException *)&v26;
  }
  return result;
}

```

## disassembly

```asm
0x18000e6a8  mov     [rsp+arg_8], rdx
0x18000e6ad  push    rbx
0x18000e6ae  push    rsi
0x18000e6af  push    rdi
0x18000e6b0  push    r12
0x18000e6b2  push    r13
0x18000e6b4  push    r14
0x18000e6b6  push    r15
0x18000e6b8  sub     rsp, 70h
0x18000e6bc  mov     r12, rdx
0x18000e6bf  mov     r14, rcx
0x18000e6c2  xor     r13d, r13d
0x18000e6c5  test    rcx, rcx
0x18000e6c8  jz      loc_18000EA01
0x18000e6ce  test    rdx, rdx
0x18000e6d1  jz      loc_18000EA01
0x18000e6d7  mov     ecx, 800h; unsigned __int64
0x18000e6dc  call    ?AllocateTestMemory@@YAPEAX_K@Z; AllocateTestMemory(unsigned __int64)
0x18000e6e1  mov     rdi, rax
0x18000e6e4  mov     [rsp+0A8h+arg_10], rax
0x18000e6ec  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000e6f0  mov     rsi, r15
0x18000e6f3  inc     rsi
0x18000e6f6  cmp     [r14+rsi*2], r13w
0x18000e6fb  jnz     short loc_18000E6F3
0x18000e6fd  mov     [rax], r13w
0x18000e701  lea     rcx, ds:2[rsi*2]; unsigned __int64
0x18000e709  call    ?AllocateTestMemory@@YAPEAX_K@Z; AllocateTestMemory(unsigned __int64)
0x18000e70e  mov     rbx, rax
0x18000e711  mov     [rsp+0A8h+arg_18], rax
0x18000e719  lea     rdx, [rsi+1]; unsigned __int64
0x18000e71d  mov     r8, r14; unsigned __int16 *
0x18000e720  mov     rcx, rbx; unsigned __int16 *
0x18000e723  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e728  test    eax, eax
0x18000e72a  jnz     loc_18000E8C3
0x18000e730  mov     r13, rdi
0x18000e733  mov     [rsp+0A8h+arg_0], rbx
0x18000e73b  xor     edx, edx
0x18000e73d  mov     r14d, edx
0x18000e740  mov     ecx, r14d
0x18000e743  cmp     rcx, rsi
0x18000e746  jnb     loc_18000E835
0x18000e74c  cmp     word ptr [rbx+rcx*2], 25h ; '%'
0x18000e751  jnz     loc_18000E82D
0x18000e757  mov     [rbx+rcx*2], dx
0x18000e75b  inc     r14d
0x18000e75e  lea     r8, [rbx+r14*2]
0x18000e762  cmp     word ptr [r8], 25h ; '%'
0x18000e767  jz      short loc_18000E77C
0x18000e769  mov     eax, r14d
0x18000e76c  cmp     rax, rsi
0x18000e76f  jnb     short loc_18000E77C
0x18000e771  inc     r14d
0x18000e774  cmp     word ptr [rbx+r14*2], 25h ; '%'
0x18000e77a  jnz     short loc_18000E769
0x18000e77c  mov     ecx, r14d
0x18000e77f  cmp     rcx, rsi
0x18000e782  jnb     loc_18000E8ED
0x18000e788  mov     [rbx+r14*2], dx
0x18000e78d  mov     r9d, 3
0x18000e793  lea     rdx, [rsp+0A8h+var_50]
0x18000e798  mov     rcx, r12
0x18000e79b  call    ?getAttribute@AttributeList@@QEAA?AUAttribute@@PEAGW4AttributeType@@@Z; AttributeList::getAttribute(ushort *,AttributeType)
0x18000e7a0  lea     rcx, [rsp+0A8h+var_50]; struct Attribute *
0x18000e7a5  call    ?ConvertAttributeValueToString@@YAPEAGAEBUAttribute@@@Z; ConvertAttributeValueToString(Attribute const &)
0x18000e7aa  mov     r12, rax
0x18000e7ad  lea     rax, [rdi+800h]
0x18000e7b4  cmp     r13, rax
0x18000e7b7  jnb     loc_18000E917
0x18000e7bd  mov     r11, rax
0x18000e7c0  sub     r11, r13
0x18000e7c3  sar     r11, 1
0x18000e7c6  mov     r8, [rsp+0A8h+arg_0]; unsigned __int16 *
0x18000e7ce  mov     rdx, r11; unsigned __int64
0x18000e7d1  mov     rcx, r13; unsigned __int16 *
0x18000e7d4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e7d9  test    eax, eax
0x18000e7db  jnz     loc_18000E949
0x18000e7e1  mov     r8, r12; unsigned __int16 *
0x18000e7e4  mov     rdx, r11; unsigned __int64
0x18000e7e7  mov     rcx, r13; unsigned __int16 *
0x18000e7ea  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e7ef  test    eax, eax
0x18000e7f1  jnz     loc_18000E97B
0x18000e7f7  mov     rcx, r12; pv
0x18000e7fa  call    cs:__imp_CoTaskMemFree
0x18000e800  lea     eax, [r14+1]
0x18000e804  lea     rax, [rbx+rax*2]
0x18000e808  mov     [rsp+0A8h+arg_0], rax
0x18000e810  mov     rax, r15
0x18000e813  xor     edx, edx
0x18000e815  inc     rax
0x18000e818  cmp     [r13+rax*2+0], dx
0x18000e81e  jnz     short loc_18000E815
0x18000e820  lea     r13, [r13+rax*2+0]
0x18000e825  mov     r12, [rsp+0A8h+arg_8]
0x18000e82d  inc     r14d
0x18000e830  jmp     loc_18000E740
0x18000e835  lea     rax, [rbx+rsi*2]
0x18000e839  mov     rdx, [rsp+0A8h+arg_0]
0x18000e841  cmp     rdx, rax
0x18000e844  jnb     short loc_18000E872
0x18000e846  lea     rax, [rdi+800h]
0x18000e84d  cmp     r13, rax
0x18000e850  jnb     loc_18000E9AD
0x18000e856  mov     r8, rdx; unsigned __int16 *
0x18000e859  mov     edx, 400h; unsigned __int64
0x18000e85e  mov     rcx, rdi; unsigned __int16 *
0x18000e861  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e866  xor     esi, esi
0x18000e868  test    eax, eax
0x18000e86a  jnz     loc_18000E9D7
0x18000e870  jmp     short loc_18000E874
0x18000e872  xor     esi, esi
0x18000e874  mov     rcx, rbx; pv
0x18000e877  call    cs:__imp_CoTaskMemFree
0x18000e87d  nop
0x18000e87e  inc     r15
0x18000e881  cmp     [rdi+r15*2], si
0x18000e886  jnz     short loc_18000E87E
0x18000e888  lea     rcx, ds:2[r15*2]; unsigned __int64
0x18000e890  call    ?AllocateTestMemory@@YAPEAX_K@Z; AllocateTestMemory(unsigned __int64)
0x18000e895  mov     rbx, rax
0x18000e898  lea     rdx, [r15+1]; unsigned __int64
0x18000e89c  mov     r8, rdi; unsigned __int16 *
0x18000e89f  mov     rcx, rax; unsigned __int16 *
0x18000e8a2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e8a7  mov     rcx, rdi; pv
0x18000e8aa  call    cs:__imp_CoTaskMemFree
0x18000e8b0  mov     rax, rbx
0x18000e8b3  add     rsp, 70h
0x18000e8b7  pop     r15
0x18000e8b9  pop     r14
0x18000e8bb  pop     r13
0x18000e8bd  pop     r12
0x18000e8bf  pop     rdi
0x18000e8c0  pop     rsi
0x18000e8c1  pop     rbx
0x18000e8c2  retn
0x18000e8c3  mov     rcx, rbx; pv
0x18000e8c6  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e8cb  mov     rcx, rdi; pv
0x18000e8ce  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e8d3  mov     [rsp+0A8h+pExceptionObject], 4
0x18000e8db  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000e8e2  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18000e8e7  call    _CxxThrowException_0
0x18000e8ed  mov     rcx, rbx; pv
0x18000e8f0  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e8f5  mov     rcx, rdi; pv
0x18000e8f8  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e8fd  mov     [rsp+0A8h+var_84], 4
0x18000e905  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000e90c  lea     rcx, [rsp+0A8h+var_84]; pExceptionObject
0x18000e911  call    _CxxThrowException_0
0x18000e917  mov     rcx, rbx; pv
0x18000e91a  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e91f  mov     rcx, rdi; pv
0x18000e922  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e927  mov     rcx, r12; pv
0x18000e92a  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e92f  mov     [rsp+0A8h+var_80], 4
0x18000e937  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000e93e  lea     rcx, [rsp+0A8h+var_80]; pExceptionObject
0x18000e943  call    _CxxThrowException_0
0x18000e949  mov     rcx, rbx; pv
0x18000e94c  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e951  mov     rcx, rdi; pv
0x18000e954  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e959  mov     rcx, r12; pv
0x18000e95c  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e961  mov     [rsp+0A8h+var_7C], 4
0x18000e969  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000e970  lea     rcx, [rsp+0A8h+var_7C]; pExceptionObject
0x18000e975  call    _CxxThrowException_0
0x18000e97b  mov     rcx, rbx; pv
0x18000e97e  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e983  mov     rcx, rdi; pv
0x18000e986  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e98b  mov     rcx, r12; pv
0x18000e98e  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e993  mov     [rsp+0A8h+var_78], 4
0x18000e99b  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000e9a2  lea     rcx, [rsp+0A8h+var_78]; pExceptionObject
0x18000e9a7  call    _CxxThrowException_0
0x18000e9ad  mov     rcx, rbx; pv
0x18000e9b0  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e9b5  mov     rcx, rdi; pv
0x18000e9b8  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e9bd  mov     [rsp+0A8h+var_70], 4
0x18000e9c5  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000e9cc  lea     rcx, [rsp+0A8h+var_70]; pExceptionObject
0x18000e9d1  call    _CxxThrowException_0
0x18000e9d7  mov     rcx, rbx; pv
0x18000e9da  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e9df  mov     rcx, rdi; pv
0x18000e9e2  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e9e7  mov     [rsp+0A8h+var_6C], 4
0x18000e9ef  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000e9f6  lea     rcx, [rsp+0A8h+var_6C]; pExceptionObject
0x18000e9fb  call    _CxxThrowException_0
0x18000ea01  mov     [rsp+0A8h+var_60], 4
0x18000ea09  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000ea10  lea     rcx, [rsp+0A8h+var_60]; pExceptionObject
0x18000ea15  call    _CxxThrowException_0
```
