# CspRemoveContainer

- ea: `0x18001e9b8`
- end: `0x18001ea9f`
- name: `CspRemoveContainer`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180010760`

## callees

- `0x18000de80`
- `0x18001dbec`
- `0x18001dd04`
- `0x18001e9b8`
- `0x18001fca8`
- `0x180020394`

## pseudocode

```c
__int64 __fastcall CspRemoveContainer(__int64 a1, __int64 a2, unsigned __int8 a3, int a4)
{
  __int64 v7; // rdx
  unsigned int v8; // edi
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  char *v12; // rbx
  char *v14[5]; // [rsp+30h] [rbp-28h] BYREF
  int v15; // [rsp+78h] [rbp+20h] BYREF

  v15 = a4;
  v14[0] = 0;
  LOBYTE(v15) = 0;
  v8 = CspBuildCertificateFilename(a1, a2, 0, 2, v14);
  if ( v8
    || (CspDeleteFile(a1, v7, v9, v14[0]),
        CspFreeH(v14[0]),
        v14[0] = 0,
        (v8 = CspBuildCertificateFilename(a1, a2, 0, 1, v14)) != 0) )
  {
    v12 = v14[0];
  }
  else
  {
    v12 = v14[0];
    CspDeleteFile(a1, v10, v11, v14[0]);
    v8 = CspDeleteContainer(a1, a3);
    if ( !v8 )
      v8 = ContainerMapDeleteContainer(a1, a2, &v15);
  }
  if ( v12 )
    CspFreeH(v12);
  return v8;
}

```

## disassembly

```asm
0x18001e9b8  mov     rax, rsp
0x18001e9bb  mov     [rax+8], rbx
0x18001e9bf  mov     [rax+10h], rbp
0x18001e9c3  mov     [rax+20h], r9d
0x18001e9c7  push    rsi
0x18001e9c8  push    rdi
0x18001e9c9  push    r14
0x18001e9cb  sub     rsp, 40h
0x18001e9cf  mov     qword ptr [rax-28h], 0
0x18001e9d7  mov     r14b, r8b
0x18001e9da  mov     byte ptr [rax+20h], 0
0x18001e9de  lea     rax, [rax-28h]
0x18001e9e2  mov     r9d, 2
0x18001e9e8  mov     [rsp+58h+var_38], rax
0x18001e9ed  xor     r8d, r8d
0x18001e9f0  mov     rbp, rdx
0x18001e9f3  mov     rsi, rcx
0x18001e9f6  call    CspBuildCertificateFilename
0x18001e9fb  mov     edi, eax
0x18001e9fd  test    eax, eax
0x18001e9ff  jnz     short loc_18001EA78
0x18001ea01  mov     r9, [rsp+58h+var_28]
0x18001ea06  mov     rcx, rsi
0x18001ea09  call    CspDeleteFile
0x18001ea0e  mov     rcx, [rsp+58h+var_28]
0x18001ea13  call    CspFreeH
0x18001ea18  lea     rax, [rsp+58h+var_28]
0x18001ea1d  mov     [rsp+58h+var_28], 0
0x18001ea26  lea     r9d, [rdi+1]
0x18001ea2a  mov     [rsp+58h+var_38], rax
0x18001ea2f  xor     r8d, r8d
0x18001ea32  mov     rdx, rbp
0x18001ea35  mov     rcx, rsi
0x18001ea38  call    CspBuildCertificateFilename
0x18001ea3d  mov     edi, eax
0x18001ea3f  test    eax, eax
0x18001ea41  jnz     short loc_18001EA78
0x18001ea43  mov     rbx, [rsp+58h+var_28]
0x18001ea48  mov     rcx, rsi
0x18001ea4b  mov     r9, rbx
0x18001ea4e  call    CspDeleteFile
0x18001ea53  mov     dl, r14b
0x18001ea56  mov     rcx, rsi
0x18001ea59  call    CspDeleteContainer
0x18001ea5e  mov     edi, eax
0x18001ea60  test    eax, eax
0x18001ea62  jnz     short loc_18001EA7D
0x18001ea64  lea     r8, [rsp+58h+arg_18]
0x18001ea69  mov     rdx, rbp
0x18001ea6c  mov     rcx, rsi
0x18001ea6f  call    ContainerMapDeleteContainer
0x18001ea74  mov     edi, eax
0x18001ea76  jmp     short loc_18001EA7D
0x18001ea78  mov     rbx, [rsp+58h+var_28]
0x18001ea7d  test    rbx, rbx
0x18001ea80  jz      short loc_18001EA8A
0x18001ea82  mov     rcx, rbx
0x18001ea85  call    CspFreeH
0x18001ea8a  mov     rbx, [rsp+58h+arg_0]
0x18001ea8f  mov     eax, edi
0x18001ea91  mov     rbp, [rsp+58h+arg_8]
0x18001ea96  add     rsp, 40h
0x18001ea9a  pop     r14
0x18001ea9c  pop     rdi
0x18001ea9d  pop     rsi
0x18001ea9e  retn
```
