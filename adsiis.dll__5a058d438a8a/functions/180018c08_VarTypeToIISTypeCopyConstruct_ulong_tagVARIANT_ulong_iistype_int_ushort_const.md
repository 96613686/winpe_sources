# VarTypeToIISTypeCopyConstruct(ulong,tagVARIANT *,ulong,_iistype * *,int,ushort const *)

- ea: `0x180018c08`
- end: `0x180018cb5`
- name: `?VarTypeToIISTypeCopyConstruct@@YAJKPEAUtagVARIANT@@KPEAPEAU_iistype@@HPEBG@Z`
- size: `173`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, struct tagVARIANT *@<rdx>, unsigned int@<r8d>, struct _iistype **@<r9>, int, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800032a0`
- `0x1800035a0`
- `0x180006f60`
- `0x180007300`
- `0x1800103bc`

## callees

- `0x1800184ac`
- `0x180018a44`
- `0x180018c08`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsMem` at `0x180018c35`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180018c35`

## pseudocode

```c
__int64 __fastcall VarTypeToIISTypeCopyConstruct(
        unsigned int a1,
        struct tagVARIANT *a2,
        unsigned int a3,
        struct _iistype **a4,
        int a5,
        unsigned __int16 *a6)
{
  struct _iistype *v10; // rdi
  __int64 result; // rax
  __int64 i; // rsi
  HRESULT v13; // ebp

  if ( a3 > 0xAAAAAAA )
    return 2147942934LL;
  v10 = (struct _iistype *)AllocADsMem(24 * a3);
  if ( !v10 )
    return 2147500037LL;
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
  {
    v13 = VarTypeToIISTypeCopy(a1, &a2[i], (struct _iistype *)((char *)v10 + 24 * i), a5, a6);
    if ( v13 < 0 )
    {
      IISTypeFreeIISObjects(v10, a3);
      result = (unsigned int)v13;
      *a4 = 0;
      return result;
    }
  }
  *a4 = v10;
  return 0;
}

```

## disassembly

```asm
0x180018c08  push    rbx
0x180018c0a  push    rbp
0x180018c0b  push    rsi
0x180018c0c  push    rdi
0x180018c0d  push    r12
0x180018c0f  push    r13
0x180018c11  push    r14
0x180018c13  push    r15
0x180018c15  sub     rsp, 38h
0x180018c19  mov     r14, r9
0x180018c1c  mov     ebx, r8d
0x180018c1f  mov     r12, rdx
0x180018c22  mov     r13d, ecx
0x180018c25  cmp     r8d, 0AAAAAAAh
0x180018c2c  ja      short loc_180018C9F
0x180018c2e  lea     ecx, [r8+r8*2]
0x180018c32  shl     ecx, 3; cb
0x180018c35  call    cs:__imp_AllocADsMem
0x180018c3b  mov     rdi, rax
0x180018c3e  test    rax, rax
0x180018c41  jnz     short loc_180018C4A
0x180018c43  mov     eax, 80004005h
0x180018c48  jmp     short loc_180018CA4
0x180018c4a  mov     r15, [rsp+78h+arg_28]
0x180018c52  xor     esi, esi
0x180018c54  cmp     esi, ebx
0x180018c56  jnb     short loc_180018C98
0x180018c58  mov     r9d, [rsp+78h+arg_20]; int
0x180018c60  lea     rcx, [rsi+rsi*2]
0x180018c64  lea     r8, [rdi+rcx*8]; struct _iistype *
0x180018c68  mov     [rsp+78h+var_58], r15; unsigned __int16 *
0x180018c6d  lea     rdx, [r12+rcx*8]; struct tagVARIANT *
0x180018c71  mov     ecx, r13d; unsigned int
0x180018c74  call    ?VarTypeToIISTypeCopy@@YAJKPEAUtagVARIANT@@PEAU_iistype@@HPEBG@Z; VarTypeToIISTypeCopy(ulong,tagVARIANT *,_iistype *,int,ushort const *)
0x180018c79  mov     ebp, eax
0x180018c7b  test    eax, eax
0x180018c7d  js      short loc_180018C83
0x180018c7f  inc     esi
0x180018c81  jmp     short loc_180018C54
0x180018c83  mov     edx, ebx; unsigned int
0x180018c85  mov     rcx, rdi; struct _iistype *
0x180018c88  call    ?IISTypeFreeIISObjects@@YAXPEAU_iistype@@K@Z; IISTypeFreeIISObjects(_iistype *,ulong)
0x180018c8d  mov     eax, ebp
0x180018c8f  mov     qword ptr [r14], 0
0x180018c96  jmp     short loc_180018CA4
0x180018c98  mov     [r14], rdi
0x180018c9b  xor     eax, eax
0x180018c9d  jmp     short loc_180018CA4
0x180018c9f  mov     eax, 80070216h
0x180018ca4  add     rsp, 38h
0x180018ca8  pop     r15
0x180018caa  pop     r14
0x180018cac  pop     r13
0x180018cae  pop     r12
0x180018cb0  pop     rdi
0x180018cb1  pop     rsi
0x180018cb2  pop     rbp
0x180018cb3  pop     rbx
0x180018cb4  retn
```
