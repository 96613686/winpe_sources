# InitServerInfo(CCredentials &,ushort const *,IMSAdminBaseW * *,IIsSchema * *)

- ea: `0x18001364c`
- end: `0x1800136ff`
- name: `?InitServerInfo@@YAJAEAVCCredentials@@PEBGPEAPEAUIMSAdminBaseW@@PEAPEAVIIsSchema@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(struct CCredentials *, const unsigned __int16 *, struct IMSAdminBaseW **, struct IIsSchema **)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x180002c80`
- `0x180003bb8`
- `0x18000474c`
- `0x1800084a8`
- `0x180009a44`
- `0x180009d90`
- `0x18000d638`
- `0x18000d83c`
- `0x180010968`
- `0x180015664`

## callees

- `0x180013378`
- `0x180013430`
- `0x18001364c`
- `0x180014624`
- `0x18001b5ec`

## pseudocode

```c
__int64 __fastcall InitServerInfo(
        struct CCredentials *a1,
        unsigned __int16 *a2,
        struct IMSAdminBaseW **a3,
        struct IIsSchema **a4)
{
  unsigned __int16 *v5; // rsi
  int inited; // ebx
  int Schema; // eax
  struct IMSAdminBaseW *v10; // rcx
  struct IMSAdminBaseW *v12; // [rsp+78h] [rbp+10h] BYREF

  v12 = 0;
  v5 = L"Localhost";
  if ( a2 )
    v5 = a2;
  inited = InitAdminBase(a1, v5, (struct IUnknown **)&v12);
  if ( inited >= 0 )
  {
    Schema = GetSchema(a1, v5);
    inited = Schema;
    if ( (_WORD)Schema == 3 || Schema == -2146646015 )
    {
      inited = -2146646000;
    }
    else if ( Schema >= 0 )
    {
      v10 = 0;
      *a4 = 0;
      *a3 = v12;
      goto LABEL_10;
    }
  }
  v10 = v12;
LABEL_10:
  if ( v10 )
    UninitAdminBase(v10);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001364c  push    rbx
0x18001364e  push    rbp
0x18001364f  push    rsi
0x180013650  push    rdi
0x180013651  push    r14
0x180013653  push    r15
0x180013655  sub     rsp, 38h
0x180013659  xor     edi, edi
0x18001365b  mov     [rsp+68h+arg_8], 0
0x180013664  test    rdx, rdx
0x180013667  mov     [rsp+68h+var_48], rdi
0x18001366c  mov     r15, r8
0x18001366f  lea     rsi, aLocalhost_1; "Localhost"
0x180013676  cmovnz  rsi, rdx
0x18001367a  lea     r8, [rsp+68h+arg_8]; struct IMSAdminBaseW **
0x18001367f  mov     rdx, rsi; unsigned __int16 *
0x180013682  mov     r14, r9
0x180013685  mov     rbp, rcx
0x180013688  call    ?InitAdminBase@@YAJAEAVCCredentials@@PEBGPEAPEAUIMSAdminBaseW@@@Z; InitAdminBase(CCredentials &,ushort const *,IMSAdminBaseW * *)
0x18001368d  mov     ebx, eax
0x18001368f  test    eax, eax
0x180013691  js      short loc_1800136D4
0x180013693  lea     r8, [rsp+68h+var_48]
0x180013698  mov     rdx, rsi; unsigned __int16 *
0x18001369b  mov     rcx, rbp; struct CCredentials *
0x18001369e  call    GetSchema
0x1800136a3  mov     ebx, eax
0x1800136a5  cmp     ax, 3
0x1800136a9  jz      short loc_1800136CA
0x1800136ab  cmp     eax, 800CC801h
0x1800136b0  jz      short loc_1800136CA
0x1800136b2  test    eax, eax
0x1800136b4  js      short loc_1800136CF
0x1800136b6  mov     rax, [rsp+68h+var_48]
0x1800136bb  xor     ecx, ecx
0x1800136bd  mov     [r14], rax
0x1800136c0  mov     rax, [rsp+68h+arg_8]
0x1800136c5  mov     [r15], rax
0x1800136c8  jmp     short loc_1800136D9
0x1800136ca  mov     ebx, 800CC810h
0x1800136cf  mov     rdi, [rsp+68h+var_48]
0x1800136d4  mov     rcx, [rsp+68h+arg_8]; struct IMSAdminBaseW *
0x1800136d9  test    rcx, rcx
0x1800136dc  jz      short loc_1800136E3
0x1800136de  call    ?UninitAdminBase@@YAXPEAUIMSAdminBaseW@@@Z; UninitAdminBase(IMSAdminBaseW *)
0x1800136e3  test    rdi, rdi
0x1800136e6  jz      short loc_1800136F0
0x1800136e8  mov     rcx, rdi; this
0x1800136eb  call    ?Release@IIsSchema@@QEAAJXZ; IIsSchema::Release(void)
0x1800136f0  mov     eax, ebx
0x1800136f2  add     rsp, 38h
0x1800136f6  pop     r15
0x1800136f8  pop     r14
0x1800136fa  pop     rdi
0x1800136fb  pop     rsi
0x1800136fc  pop     rbp
0x1800136fd  pop     rbx
0x1800136fe  retn
```
