# CIISNamespace::OpenDSObject(ushort *,ushort *,ushort *,long,IDispatch * *)

- ea: `0x1800022c0`
- end: `0x18000236d`
- name: `?OpenDSObject@CIISNamespace@@UEAAJPEAG00JPEAPEAUIDispatch@@@Z`
- size: `173`
- prototype: `__int64 __fastcall(CIISNamespace *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int, struct IDispatch **)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1800022c0`
- `0x180015664`
- `0x1800198b4`
- `0x180019948`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CIISNamespace::OpenDSObject(
        CIISNamespace *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5,
        struct IDispatch **a6)
{
  CCredentials *v8; // rdi
  int ObjectW; // ebx
  void *v11; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 || !a6 )
    return 2147500035LL;
  v8 = (CIISNamespace *)((char *)this + 48);
  v11 = 0;
  ObjectW = CCredentials::SetUserName((CIISNamespace *)((char *)this + 48), a3);
  if ( ObjectW >= 0 )
  {
    ObjectW = CCredentials::SetPassword(v8, a4);
    if ( ObjectW >= 0 )
    {
      ObjectW = GetObjectW(a2, v8, &v11);
      if ( ObjectW >= 0 )
        ObjectW = (**(__int64 (__fastcall ***)(void *, GUID *, struct IDispatch **))v11)(v11, &IID_IDispatch, a6);
    }
  }
  if ( v11 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)ObjectW;
}

```

## disassembly

```asm
0x1800022c0  push    rbx
0x1800022c2  push    rbp
0x1800022c3  push    rdi
0x1800022c4  push    r14
0x1800022c6  sub     rsp, 28h
0x1800022ca  mov     r14, r9
0x1800022cd  mov     rbp, rdx
0x1800022d0  test    rdx, rdx
0x1800022d3  jz      loc_18000235E
0x1800022d9  cmp     [rsp+48h+arg_28], 0
0x1800022df  jz      short loc_18000235E
0x1800022e1  lea     rdi, [rcx+30h]
0x1800022e5  mov     [rsp+48h+arg_8], 0
0x1800022ee  mov     rcx, rdi; this
0x1800022f1  mov     rdx, r8; unsigned __int16 *
0x1800022f4  call    ?SetUserName@CCredentials@@QEAAJPEBG@Z; CCredentials::SetUserName(ushort const *)
0x1800022f9  mov     ebx, eax
0x1800022fb  test    eax, eax
0x1800022fd  js      short loc_180002344
0x1800022ff  mov     rdx, r14; unsigned __int16 *
0x180002302  mov     rcx, rdi; this
0x180002305  call    ?SetPassword@CCredentials@@QEAAJPEBG@Z; CCredentials::SetPassword(ushort const *)
0x18000230a  mov     ebx, eax
0x18000230c  test    eax, eax
0x18000230e  js      short loc_180002344
0x180002310  lea     r8, [rsp+48h+arg_8]; void **
0x180002315  mov     rdx, rdi; struct CCredentials *
0x180002318  mov     rcx, rbp; unsigned __int16 *
0x18000231b  call    ?GetObjectW@@YAJPEAGAEAVCCredentials@@PEAPEAX@Z; GetObjectW(ushort *,CCredentials &,void * *)
0x180002320  mov     ebx, eax
0x180002322  test    eax, eax
0x180002324  js      short loc_180002344
0x180002326  mov     rcx, [rsp+48h+arg_8]
0x18000232b  lea     rdx, IID_IDispatch
0x180002332  mov     r8, [rsp+48h+arg_28]
0x180002337  mov     rax, [rcx]
0x18000233a  mov     rax, [rax]
0x18000233d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002342  mov     ebx, eax
0x180002344  mov     rcx, [rsp+48h+arg_8]
0x180002349  test    rcx, rcx
0x18000234c  jz      short loc_18000235A
0x18000234e  mov     rax, [rcx]
0x180002351  mov     rax, [rax+10h]
0x180002355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000235a  mov     eax, ebx
0x18000235c  jmp     short loc_180002363
0x18000235e  mov     eax, 80004003h
0x180002363  add     rsp, 28h
0x180002367  pop     r14
0x180002369  pop     rdi
0x18000236a  pop     rbp
0x18000236b  pop     rbx
0x18000236c  retn
```
