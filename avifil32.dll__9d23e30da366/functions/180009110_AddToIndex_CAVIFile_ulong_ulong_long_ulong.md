# AddToIndex(CAVIFile *,ulong,ulong,long,ulong)

- ea: `0x180009110`
- end: `0x1800091ca`
- name: `?AddToIndex@@YAHPEAVCAVIFile@@KKJK@Z`
- size: `186`
- prototype: `__int64 __fastcall(struct CAVIFile *, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180009800`
- `0x18000a060`
- `0x18000c410`

## callees

- `0x180001460`
- `0x180009110`
- `0x180014eec`

## pseudocode

```c
__int64 __fastcall AddToIndex(struct CAVIFile *a1, unsigned int a2, unsigned int a3, unsigned int a4, unsigned int a5)
{
  int *v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // edx
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int v12[4]; // [rsp+30h] [rbp-28h] BYREF

  v6 = (int *)*((_QWORD *)a1 + 156);
  v12[2] = a4;
  v12[0] = a2;
  v12[3] = a3;
  v12[1] = a5;
  result = (__int64)IndexAddFileIndex(v6, v12, 1, 0, 0);
  v8 = result;
  if ( result )
  {
    if ( result != *((_QWORD *)a1 + 156) )
    {
      v9 = 0;
      for ( *((_QWORD *)a1 + 156) = result; v9 < *((_DWORD *)a1 + 26); ++v9 )
      {
        v10 = *(_QWORD *)(*((_QWORD *)a1 + v9 + 92) + 1400LL);
        if ( v10 )
          *(_QWORD *)(v10 + 8) = v8;
      }
      v11 = *((_QWORD *)a1 + 157);
      if ( v11 )
        *(_QWORD *)(v11 + 32) = v8;
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180009110  push    rbx
0x180009112  sub     rsp, 50h
0x180009116  mov     rax, cs:__security_cookie
0x18000911d  xor     rax, rsp
0x180009120  mov     [rsp+58h+var_18], rax
0x180009125  mov     eax, [rsp+58h+arg_20]
0x18000912c  mov     rbx, rcx
0x18000912f  mov     rcx, [rcx+4E0h]; pMem
0x180009136  mov     [rsp+58h+var_20], r9d
0x18000913b  xor     r9d, r9d
0x18000913e  mov     [rsp+58h+var_28], edx
0x180009142  lea     rdx, [rsp+58h+var_28]
0x180009147  mov     [rsp+58h+var_1C], r8d
0x18000914c  mov     [rsp+58h+var_24], eax
0x180009150  lea     r8d, [r9+1]
0x180009154  mov     [rsp+58h+var_38], 0; int
0x18000915c  call    IndexAddFileIndex
0x180009161  mov     r8, rax
0x180009164  test    rax, rax
0x180009167  jz      short loc_1800091B7
0x180009169  cmp     r8, [rbx+4E0h]
0x180009170  jz      short loc_1800091B2
0x180009172  xor     edx, edx
0x180009174  mov     [rbx+4E0h], r8
0x18000917b  cmp     [rbx+68h], edx
0x18000917e  jle     short loc_1800091A2
0x180009180  movsxd  rax, edx
0x180009183  mov     rcx, [rbx+rax*8+2E0h]
0x18000918b  mov     rax, [rcx+578h]
0x180009192  test    rax, rax
0x180009195  jz      short loc_18000919B
0x180009197  mov     [rax+8], r8
0x18000919b  inc     edx
0x18000919d  cmp     edx, [rbx+68h]
0x1800091a0  jl      short loc_180009180
0x1800091a2  mov     rcx, [rbx+4E8h]
0x1800091a9  test    rcx, rcx
0x1800091ac  jz      short loc_1800091B2
0x1800091ae  mov     [rcx+20h], r8
0x1800091b2  mov     eax, 1
0x1800091b7  mov     rcx, [rsp+58h+var_18]
0x1800091bc  xor     rcx, rsp; StackCookie
0x1800091bf  call    __security_check_cookie
0x1800091c4  add     rsp, 50h
0x1800091c8  pop     rbx
0x1800091c9  retn
```
