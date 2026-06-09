# RetrieveAndValidateFile(IShellItem *,IUnknown *,ushort *,ulong *)

- ea: `0x18000e324`
- end: `0x18000e437`
- name: `?RetrieveAndValidateFile@@YAHPEAUIShellItem@@PEAUIUnknown@@PEAGPEAK@Z`
- size: `275`
- prototype: `__int64 __fastcall(struct IShellItem *, struct IUnknown *, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180009710`
- `0x18000c630`

## callees

- `0x18000dfe0`
- `0x18000e324`
- `0x18000fb14`
- `0x180017010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000e422`
- `ole32!CoTaskMemFree` at `0x18000e422`

## pseudocode

```c
__int64 __fastcall RetrieveAndValidateFile(
        struct IShellItem *a1,
        struct IUnknown *a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  unsigned int v7; // edi
  unsigned __int64 v8; // rdx
  unsigned __int16 *v9; // r8
  __int64 v10; // rcx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rcx
  int v14; // [rsp+20h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+28h] [rbp-10h] BYREF
  int v16; // [rsp+70h] [rbp+38h] BYREF

  pv[0] = 0;
  v14 = 0;
  v16 = 0;
  v7 = 0;
  if ( a1 )
  {
    if ( ((int (__fastcall *)(struct IShellItem *, __int64, LPVOID *))a1->lpVtbl->GetDisplayName)(a1, 2147844096LL, pv) >= 0 )
    {
      v8 = *a4;
      if ( *a4 )
      {
        if ( v8 <= 0x7FFFFFFF )
        {
          v9 = (unsigned __int16 *)pv[0];
          v10 = 2147483646;
          v11 = a3;
          do
          {
            if ( !v10 )
              break;
            if ( !*v9 )
              break;
            *v11++ = *v9++;
            --v10;
            --v8;
          }
          while ( v8 );
          v12 = v11 - 1;
          if ( v8 )
            v12 = v11;
          *v12 = 0;
          if ( v8
            && (unsigned int)ValidateExecutableFile(a3, &v14, &v16)
            && (!v14 && !v16
             || (unsigned int)ResolveLink(a2, a3, a4) && (unsigned int)ValidateExecutableFile(a3, &v14, &v16)) )
          {
            v7 = 1;
          }
        }
        else
        {
          *a3 = 0;
        }
      }
    }
  }
  CoTaskMemFree(pv[0]);
  return v7;
}

```

## disassembly

```asm
0x18000e324  push    rbp
0x18000e326  push    rbx
0x18000e327  push    rsi
0x18000e328  push    rdi
0x18000e329  push    r14
0x18000e32b  push    r15
0x18000e32d  mov     rbp, rsp
0x18000e330  sub     rsp, 38h
0x18000e334  xor     r15d, r15d
0x18000e337  mov     rsi, r9
0x18000e33a  mov     [rbp+pv], r15
0x18000e33e  mov     rbx, r8
0x18000e341  mov     [rbp+var_18], r15d
0x18000e345  mov     r14, rdx
0x18000e348  mov     [rbp+arg_0], r15d
0x18000e34c  mov     edi, r15d
0x18000e34f  test    rcx, rcx
0x18000e352  jz      loc_18000E41E
0x18000e358  mov     rax, [rcx]
0x18000e35b  lea     r8, [rbp+pv]
0x18000e35f  mov     edx, 80058000h
0x18000e364  mov     rax, [rax+28h]
0x18000e368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e36d  test    eax, eax
0x18000e36f  js      loc_18000E41E
0x18000e375  mov     edx, [rsi]
0x18000e377  test    rdx, rdx
0x18000e37a  jz      loc_18000E41E
0x18000e380  cmp     rdx, 7FFFFFFFh
0x18000e387  jbe     short loc_18000E392
0x18000e389  mov     [rbx], r15w
0x18000e38d  jmp     loc_18000E41E
0x18000e392  mov     r8, [rbp+pv]
0x18000e396  mov     ecx, 7FFFFFFEh
0x18000e39b  mov     rax, rbx
0x18000e39e  test    rcx, rcx
0x18000e3a1  jz      short loc_18000E3C2
0x18000e3a3  movzx   r9d, word ptr [r8]
0x18000e3a7  test    r9w, r9w
0x18000e3ab  jz      short loc_18000E3C2
0x18000e3ad  mov     [rax], r9w
0x18000e3b1  add     r8, 2
0x18000e3b5  add     rax, 2
0x18000e3b9  dec     rcx
0x18000e3bc  sub     rdx, 1
0x18000e3c0  jnz     short loc_18000E39E
0x18000e3c2  test    rdx, rdx
0x18000e3c5  lea     rcx, [rax-2]
0x18000e3c9  cmovnz  rcx, rax
0x18000e3cd  mov     [rcx], r15w
0x18000e3d1  jz      short loc_18000E41E
0x18000e3d3  lea     r8, [rbp+arg_0]; int *
0x18000e3d7  mov     rcx, rbx; String1
0x18000e3da  lea     rdx, [rbp+var_18]; int *
0x18000e3de  call    ?ValidateExecutableFile@@YAHPEAGPEAH1@Z; ValidateExecutableFile(ushort *,int *,int *)
0x18000e3e3  test    eax, eax
0x18000e3e5  jz      short loc_18000E41E
0x18000e3e7  cmp     [rbp+var_18], r15d
0x18000e3eb  jnz     short loc_18000E3F3
0x18000e3ed  cmp     [rbp+arg_0], r15d
0x18000e3f1  jz      short loc_18000E419
0x18000e3f3  mov     r8, rsi; unsigned int *
0x18000e3f6  mov     rdx, rbx; unsigned __int16 *
0x18000e3f9  mov     rcx, r14; punk
0x18000e3fc  call    ?ResolveLink@@YAHPEAUIUnknown@@PEAGPEAK@Z; ResolveLink(IUnknown *,ushort *,ulong *)
0x18000e401  test    eax, eax
0x18000e403  jz      short loc_18000E41E
0x18000e405  lea     r8, [rbp+arg_0]; int *
0x18000e409  mov     rcx, rbx; String1
0x18000e40c  lea     rdx, [rbp+var_18]; int *
0x18000e410  call    ?ValidateExecutableFile@@YAHPEAGPEAH1@Z; ValidateExecutableFile(ushort *,int *,int *)
0x18000e415  test    eax, eax
0x18000e417  jz      short loc_18000E41E
0x18000e419  mov     edi, 1
0x18000e41e  mov     rcx, [rbp+pv]; pv
0x18000e422  call    cs:__imp_CoTaskMemFree
0x18000e428  mov     eax, edi
0x18000e42a  add     rsp, 38h
0x18000e42e  pop     r15
0x18000e430  pop     r14
0x18000e432  pop     rdi
0x18000e433  pop     rsi
0x18000e434  pop     rbx
0x18000e435  pop     rbp
0x18000e436  retn
```
