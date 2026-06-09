# CIISNamespaceCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180001cc0`
- end: `0x180001d3b`
- name: `?CreateInstance@CIISNamespaceCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `123`
- prototype: `int(CIISNamespaceCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001cc0`
- `0x18000204c`
- `0x180019590`
- `0x18001984c`

## pseudocode

```c
__int64 __fastcall CIISNamespaceCF::CreateInstance(
        CIISNamespaceCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  const unsigned __int16 *v7; // rdx
  const unsigned __int16 *v8; // rcx
  __int64 v9; // r9
  unsigned int Namespace; // ebx
  _BYTE v12[40]; // [rsp+30h] [rbp-28h] BYREF

  CCredentials::Initialize((CCredentials *)v12, 0, 0, 0);
  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
      Namespace = -2147467259;
    else
      Namespace = CIISNamespace::CreateNamespace(v8, v7, (struct CCredentials *)v12, v9, a3, a4);
  }
  else
  {
    Namespace = -2147467261;
  }
  CCredentials::~CCredentials((CCredentials *)v12);
  return Namespace;
}

```

## disassembly

```asm
0x180001cc0  mov     [rsp+arg_0], rbx
0x180001cc5  mov     [rsp+arg_8], rsi
0x180001cca  push    rdi
0x180001ccb  sub     rsp, 50h
0x180001ccf  mov     rbx, r9
0x180001cd2  lea     rcx, [rsp+58h+var_28]; this
0x180001cd7  mov     rsi, r8
0x180001cda  mov     rdi, rdx
0x180001cdd  xor     r9d, r9d; unsigned int
0x180001ce0  xor     r8d, r8d; unsigned __int16 *
0x180001ce3  xor     edx, edx; unsigned __int16 *
0x180001ce5  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x180001cea  test    rbx, rbx
0x180001ced  jnz     short loc_180001CF6
0x180001cef  mov     ebx, 80004003h
0x180001cf4  jmp     short loc_180001D1F
0x180001cf6  mov     qword ptr [rbx], 0
0x180001cfd  test    rdi, rdi
0x180001d00  jz      short loc_180001D09
0x180001d02  mov     ebx, 80004005h
0x180001d07  jmp     short loc_180001D1F
0x180001d09  mov     [rsp+58h+var_30], rbx; void **
0x180001d0e  lea     r8, [rsp+58h+var_28]; struct CCredentials *
0x180001d13  mov     [rsp+58h+var_38], rsi; struct _GUID *
0x180001d18  call    ?CreateNamespace@CIISNamespace@@SAJPEBG0AEAVCCredentials@@KAEBU_GUID@@PEAPEAX@Z; CIISNamespace::CreateNamespace(ushort const *,ushort const *,CCredentials &,ulong,_GUID const &,void * *)
0x180001d1d  mov     ebx, eax
0x180001d1f  lea     rcx, [rsp+58h+var_28]; this
0x180001d24  call    ??1CCredentials@@QEAA@XZ; CCredentials::~CCredentials(void)
0x180001d29  mov     rsi, [rsp+58h+arg_8]
0x180001d2e  mov     eax, ebx
0x180001d30  mov     rbx, [rsp+58h+arg_0]
0x180001d35  add     rsp, 50h
0x180001d39  pop     rdi
0x180001d3a  retn
```
