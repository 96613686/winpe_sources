# CIISClass::IISCreateObject(void)

- ea: `0x18000a860`
- end: `0x18000a8fa`
- name: `?IISCreateObject@CIISClass@@QEAAJXZ`
- size: `154`
- prototype: `__int64 __fastcall(CIISClass *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000be90`

## callees

- `0x18000a860`
- `0x180012ffc`
- `0x18001441c`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CIISClass::IISCreateObject(unsigned __int16 **this)
{
  struct IMSAdminBaseW **v2; // rsi
  int v3; // edi
  unsigned int v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = 0;
  v2 = (struct IMSAdminBaseW **)(this + 37);
  v3 = OpenAdminBaseKey(
         (struct CCredentials *)(this + 33),
         this[30],
         L"Schema/Classes",
         2u,
         (struct IMSAdminBaseW **)this + 37,
         &v5);
  if ( v3 >= 0 )
    v3 = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, unsigned __int16 *))(*v2)->lpVtbl->AddKey)(
           *v2,
           v5,
           this[31]);
  if ( *v2 && v5 )
    CloseAdminBaseKey(*v2, v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000a860  mov     r11, rsp
0x18000a863  mov     [r11+10h], rbp
0x18000a867  mov     [r11+18h], rsi
0x18000a86b  push    rdi
0x18000a86c  sub     rsp, 30h
0x18000a870  mov     rbp, rcx
0x18000a873  mov     [rsp+38h+arg_0], 0
0x18000a87b  lea     rsi, [rcx+128h]
0x18000a882  mov     r9d, 2; unsigned int
0x18000a888  lea     rax, [r11+8]
0x18000a88c  add     rcx, 108h; this
0x18000a893  mov     [r11-10h], rax
0x18000a897  lea     r8, aSchemaClasses; "Schema/Classes"
0x18000a89e  mov     rdx, [rbp+0F0h]; unsigned __int16 *
0x18000a8a5  mov     [r11-18h], rsi
0x18000a8a9  call    ?OpenAdminBaseKey@@YAJAEAVCCredentials@@PEAG1KPEAPEAUIMSAdminBaseW@@PEAK@Z; OpenAdminBaseKey(CCredentials &,ushort *,ushort *,ulong,IMSAdminBaseW * *,ulong *)
0x18000a8ae  mov     edi, eax
0x18000a8b0  test    eax, eax
0x18000a8b2  js      short loc_18000A8D0
0x18000a8b4  mov     rcx, [rsi]
0x18000a8b7  mov     r8, [rbp+0F8h]
0x18000a8be  mov     edx, [rsp+38h+arg_0]
0x18000a8c2  mov     rax, [rcx]
0x18000a8c5  mov     rax, [rax+18h]
0x18000a8c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8ce  mov     edi, eax
0x18000a8d0  mov     rcx, [rsi]; struct IMSAdminBaseW *
0x18000a8d3  test    rcx, rcx
0x18000a8d6  jz      short loc_18000A8E8
0x18000a8d8  cmp     [rsp+38h+arg_0], 0
0x18000a8dd  jz      short loc_18000A8E8
0x18000a8df  mov     edx, [rsp+38h+arg_0]; unsigned int
0x18000a8e3  call    ?CloseAdminBaseKey@@YAXPEAUIMSAdminBaseW@@K@Z; CloseAdminBaseKey(IMSAdminBaseW *,ulong)
0x18000a8e8  mov     rbp, [rsp+38h+arg_8]
0x18000a8ed  mov     eax, edi
0x18000a8ef  mov     rsi, [rsp+38h+arg_10]
0x18000a8f4  add     rsp, 30h
0x18000a8f8  pop     rdi
0x18000a8f9  retn
```
