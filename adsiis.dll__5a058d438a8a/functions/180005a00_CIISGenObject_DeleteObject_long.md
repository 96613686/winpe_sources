# CIISGenObject::DeleteObject(long)

- ea: `0x180005a00`
- end: `0x180005a85`
- name: `?DeleteObject@CIISGenObject@@UEAAJJ@Z`
- size: `133`
- prototype: `__int64 __fastcall(CIISGenObject *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005a00`
- `0x180012ffc`
- `0x18001441c`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CIISGenObject::DeleteObject(unsigned __int16 **this, int a2)
{
  unsigned int v2; // edi
  struct IMSAdminBaseW **v3; // rbx
  unsigned int v5; // ebp
  int v6; // eax
  unsigned int v8; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  v3 = (struct IMSAdminBaseW **)(this + 14);
  v8 = 0;
  if ( a2 )
  {
    v5 = -2147024809;
  }
  else
  {
    v6 = OpenAdminBaseKey((struct CCredentials *)(this + 11), this[6], 0, 2u, v3, &v8);
    v2 = v8;
    v5 = v6;
    if ( v6 >= 0 )
      v5 = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, unsigned __int16 *))(*v3)->lpVtbl->DeleteKey)(
             *v3,
             v8,
             this[7]);
  }
  if ( *v3 && v2 )
    CloseAdminBaseKey(*v3, v2);
  return v5;
}

```

## disassembly

```asm
0x180005a00  push    rbx
0x180005a02  push    rbp
0x180005a03  push    rsi
0x180005a04  push    rdi
0x180005a05  sub     rsp, 38h
0x180005a09  xor     edi, edi
0x180005a0b  lea     rbx, [rcx+70h]
0x180005a0f  mov     [rsp+58h+arg_8], edi
0x180005a13  mov     rsi, rcx
0x180005a16  test    edx, edx
0x180005a18  jz      short loc_180005A21
0x180005a1a  mov     ebp, 80070057h
0x180005a1f  jmp     short loc_180005A67
0x180005a21  mov     rdx, [rsi+30h]; unsigned __int16 *
0x180005a25  lea     rax, [rsp+58h+arg_8]
0x180005a2a  mov     [rsp+58h+var_30], rax; unsigned int *
0x180005a2f  add     rcx, 58h ; 'X'; this
0x180005a33  mov     r9d, 2; unsigned int
0x180005a39  mov     [rsp+58h+var_38], rbx; struct IMSAdminBaseW **
0x180005a3e  xor     r8d, r8d; unsigned __int16 *
0x180005a41  call    ?OpenAdminBaseKey@@YAJAEAVCCredentials@@PEAG1KPEAPEAUIMSAdminBaseW@@PEAK@Z; OpenAdminBaseKey(CCredentials &,ushort *,ushort *,ulong,IMSAdminBaseW * *,ulong *)
0x180005a46  mov     edi, [rsp+58h+arg_8]
0x180005a4a  mov     ebp, eax
0x180005a4c  test    eax, eax
0x180005a4e  js      short loc_180005A67
0x180005a50  mov     rcx, [rbx]
0x180005a53  mov     edx, edi
0x180005a55  mov     r8, [rsi+38h]
0x180005a59  mov     rax, [rcx]
0x180005a5c  mov     rax, [rax+20h]
0x180005a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a65  mov     ebp, eax
0x180005a67  mov     rcx, [rbx]; struct IMSAdminBaseW *
0x180005a6a  test    rcx, rcx
0x180005a6d  jz      short loc_180005A7A
0x180005a6f  test    edi, edi
0x180005a71  jz      short loc_180005A7A
0x180005a73  mov     edx, edi; unsigned int
0x180005a75  call    ?CloseAdminBaseKey@@YAXPEAUIMSAdminBaseW@@K@Z; CloseAdminBaseKey(IMSAdminBaseW *,ulong)
0x180005a7a  mov     eax, ebp
0x180005a7c  add     rsp, 38h
0x180005a80  pop     rdi
0x180005a81  pop     rsi
0x180005a82  pop     rbp
0x180005a83  pop     rbx
0x180005a84  retn
```
