# RBiPtSrvCreateEventForApp

- ea: `0x180031300`
- end: `0x1800315a2`
- name: `RBiPtSrvCreateEventForApp`
- size: `674`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE BindingHandle@<rcx>, int, int, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000c928`
- `0x180031300`
- `0x1800317f0`
- `0x180031f20`
- `0x180032478`
- `0x18004df58`
- `0x180094662`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180031504`
- `ntdll!RtlFreeHeap` at `0x18003155d`
- `ntdll!RtlFreeHeap` at `0x180031504`
- `ntdll!RtlFreeHeap` at `0x18003155d`
- `ntdll!RtlAllocateHeap` at `0x180031570`
- `ntdll!RtlAllocateHeap` at `0x180031570`
- `RPCRT4!RpcRevertToSelf` at `0x180031429`
- `RPCRT4!RpcRevertToSelf` at `0x180031429`
- `RPCRT4!RpcImpersonateClient` at `0x1800313f5`
- `RPCRT4!RpcImpersonateClient` at `0x1800313f5`

## pseudocode

```c
__int64 __fastcall RBiPtSrvCreateEventForApp(
        RPC_BINDING_HANDLE BindingHandle,
        __int64 a2,
        _QWORD *a3,
        const void *a4,
        unsigned int a5,
        int a6,
        __int64 a7)
{
  unsigned __int16 v10; // si
  _QWORD *v11; // rcx
  int ClientInformation; // ebx
  __int64 v14; // rax
  __int64 *v15; // r15
  _BYTE *Heap; // rdi
  int v17; // eax
  __int64 v18; // rdx
  int Source1; // [rsp+20h] [rbp-E0h]
  __int16 v20; // [rsp+60h] [rbp-A0h] BYREF
  int v21[2]; // [rsp+68h] [rbp-98h]
  __int64 Sid[10]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v23[256]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE P[512]; // [rsp+1C0h] [rbp+C0h] BYREF

  *(_QWORD *)v21 = a2;
  memset_0(Sid, 0, 0x44u);
  v10 = 0;
  if ( !a3 )
    goto LABEL_2;
  v14 = *a3 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *a3 == *(_QWORD *)&GUID_NULL.Data1 )
    v14 = a3[1] - *(_QWORD *)GUID_NULL.Data4;
  if ( !v14 )
  {
LABEL_2:
    v11 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return (unsigned int)-1073741811;
    v18 = 15;
    goto LABEL_34;
  }
  v15 = 0;
  if ( a4 )
  {
    if ( (unsigned __int8)BipValidatePackageFullNameSizeInput(a5) )
    {
      memset_0(v23, 0, sizeof(v23));
      memcpy_0(v23, a4, 2LL * a5);
      v15 = (__int64 *)v23;
      goto LABEL_11;
    }
    v11 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return (unsigned int)-1073741811;
    v18 = 16;
LABEL_34:
    WPP_SF_(v11[2], v18, WPP_1ffc61b1bad13c8996c8de60b3700ee4_Traceguids);
    return (unsigned int)-1073741811;
  }
LABEL_11:
  if ( RpcImpersonateClient(BindingHandle) )
    return (unsigned int)-1073741823;
  ClientInformation = BipQueryClientInformation(Sid, 0, 0, 0, Source1, 0, 0, 1);
  if ( RpcRevertToSelf() )
  {
    return (unsigned int)-1073741823;
  }
  else if ( ClientInformation >= 0 )
  {
    Heap = 0;
    if ( !a7 )
      goto LABEL_20;
    v10 = 512;
    Heap = P;
    v20 = 512;
    ClientInformation = 0;
    while ( 1 )
    {
      if ( ClientInformation == -1073741789 )
      {
        if ( Heap != P )
          RtlFreeHeap(BipHeap, 0, Heap);
        Heap = RtlAllocateHeap(BipHeap, 0, v10);
      }
      if ( !Heap )
        break;
      v17 = BrpEncodeBrokeredEvent_V1(a7, v10, Heap, &v20);
      v10 = v20;
      ClientInformation = v17;
      if ( v17 != -1073741789 )
        goto LABEL_19;
    }
    ClientInformation = -1073741801;
LABEL_19:
    if ( ClientInformation >= 0 )
LABEL_20:
      ClientInformation = BiSrvCreateEvent(*(__int64 *)v21, 20, a6, (__int64)a3, 0, v15, Sid, 0, 0, Heap, v10, 0);
    if ( Heap && Heap != P )
      RtlFreeHeap(BipHeap, 0, Heap);
  }
  return (unsigned int)ClientInformation;
}

```

## disassembly

```asm
0x180031300  push    rbp
0x180031302  push    rbx
0x180031303  push    rsi
0x180031304  push    rdi
0x180031305  push    r12
0x180031307  push    r13
0x180031309  push    r14
0x18003130b  push    r15
0x18003130d  lea     rbp, [rsp-2D8h]
0x180031315  sub     rsp, 3D8h
0x18003131c  mov     rax, cs:__security_cookie
0x180031323  xor     rax, rsp
0x180031326  mov     [rbp+310h+var_50], rax
0x18003132d  mov     r13, [rbp+310h+arg_30]
0x180031334  mov     r14, r8
0x180031337  mov     qword ptr [rsp+410h+var_3A8], rdx
0x18003133c  mov     r12, rcx
0x18003133f  xor     edx, edx; Val
0x180031341  lea     rcx, [rsp+410h+Sid]; void *
0x180031346  mov     rdi, r9
0x180031349  lea     r8d, [rdx+44h]; Size
0x18003134d  call    memset_0
0x180031352  xor     esi, esi
0x180031354  test    r14, r14
0x180031357  jnz     short loc_180031394
0x180031359  mov     rcx, cs:WPP_GLOBAL_Control
0x180031360  test    byte ptr [rcx+1Ch], 40h
0x180031364  jnz     loc_18003157E
0x18003136a  mov     ebx, 0C000000Dh
0x18003136f  mov     eax, ebx
0x180031371  mov     rcx, [rbp+310h+var_50]
0x180031378  xor     rcx, rsp; StackCookie
0x18003137b  call    __security_check_cookie
0x180031380  add     rsp, 3D8h
0x180031387  pop     r15
0x180031389  pop     r14
0x18003138b  pop     r13
0x18003138d  pop     r12
0x18003138f  pop     rdi
0x180031390  pop     rsi
0x180031391  pop     rbx
0x180031392  pop     rbp
0x180031393  retn
0x180031394  mov     rax, [r14]
0x180031397  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18003139e  jnz     short loc_1800313AB
0x1800313a0  mov     rax, [r14+8]
0x1800313a4  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800313ab  test    rax, rax
0x1800313ae  jz      short loc_180031359
0x1800313b0  xor     r15d, r15d
0x1800313b3  test    rdi, rdi
0x1800313b6  jz      short loc_1800313F2
0x1800313b8  mov     ebx, [rbp+310h+arg_20]
0x1800313be  mov     ecx, ebx
0x1800313c0  call    BipValidatePackageFullNameSizeInput
0x1800313c5  test    al, al
0x1800313c7  jz      loc_180031519
0x1800313cd  xor     edx, edx; Val
0x1800313cf  lea     rcx, [rbp+310h+var_350]; void *
0x1800313d3  mov     r8d, 100h; Size
0x1800313d9  call    memset_0
0x1800313de  lea     r8, [rbx+rbx]; Size
0x1800313e2  mov     rdx, rdi; Src
0x1800313e5  lea     rcx, [rbp+310h+var_350]; void *
0x1800313e9  call    memcpy_0
0x1800313ee  lea     r15, [rbp+310h+var_350]
0x1800313f2  mov     rcx, r12; BindingHandle
0x1800313f5  call    cs:__imp_RpcImpersonateClient
0x1800313fb  xor     r12d, r12d
0x1800313fe  test    eax, eax
0x180031400  jnz     loc_18003153B
0x180031406  mov     [rsp+410h+var_3D8], 1; char
0x18003140b  lea     rcx, [rsp+410h+Sid]; Sid
0x180031410  mov     [rsp+410h+Sid1], r12; __int64
0x180031415  xor     r9d, r9d
0x180031418  xor     r8d, r8d; void *
0x18003141b  mov     [rsp+410h+var_3E8], r12; PVOID
0x180031420  xor     edx, edx; void *
0x180031422  call    BipQueryClientInformation
0x180031427  mov     ebx, eax
0x180031429  call    cs:__imp_RpcRevertToSelf
0x18003142f  test    eax, eax
0x180031431  jnz     loc_18003153B
0x180031437  test    ebx, ebx
0x180031439  js      loc_18003136F
0x18003143f  mov     edi, r12d
0x180031442  test    r13, r13
0x180031445  jz      short loc_180031495
0x180031447  mov     esi, 200h
0x18003144c  lea     rdi, [rbp+310h+P]
0x180031453  mov     [rsp+410h+var_3B0], si
0x180031458  mov     ebx, r12d
0x18003145b  cmp     ebx, 0C0000023h
0x180031461  jz      loc_180031545
0x180031467  test    rdi, rdi
0x18003146a  jz      loc_18003150F
0x180031470  lea     r9, [rsp+410h+var_3B0]
0x180031475  mov     r8, rdi
0x180031478  movzx   edx, si
0x18003147b  mov     rcx, r13
0x18003147e  call    BrpEncodeBrokeredEvent_V1
0x180031483  movzx   esi, [rsp+410h+var_3B0]
0x180031488  mov     ebx, eax
0x18003148a  cmp     eax, 0C0000023h
0x18003148f  jz      short loc_18003145B
0x180031491  test    ebx, ebx
0x180031493  js      short loc_1800314DF
0x180031495  mov     r8d, [rbp+310h+arg_28]; int
0x18003149c  mov     r9, r14; int
0x18003149f  mov     rcx, qword ptr [rsp+410h+var_3A8]; int
0x1800314a4  mov     edx, 14h; int
0x1800314a9  mov     [rsp+410h+var_3B8], r12; __int64
0x1800314ae  movzx   eax, si
0x1800314b1  mov     [rsp+410h+var_3C0], eax; int
0x1800314b5  lea     rax, [rsp+410h+Sid]
0x1800314ba  mov     [rsp+410h+var_3C8], rdi; __int64
0x1800314bf  mov     [rsp+410h+var_3D0], r12d; int
0x1800314c4  mov     qword ptr [rsp+410h+var_3D8], r12; __int64
0x1800314c9  mov     [rsp+410h+Sid1], rax; Sid1
0x1800314ce  mov     [rsp+410h+var_3E8], r15; __int64
0x1800314d3  mov     [rsp+410h+Source1], r12; Source1
0x1800314d8  call    BiSrvCreateEvent
0x1800314dd  mov     ebx, eax
0x1800314df  test    rdi, rdi
0x1800314e2  jz      loc_18003136F
0x1800314e8  lea     rax, [rbp+310h+P]
0x1800314ef  cmp     rdi, rax
0x1800314f2  jz      loc_18003136F
0x1800314f8  mov     rcx, cs:BipHeap; HeapHandle
0x1800314ff  mov     r8, rdi; P
0x180031502  xor     edx, edx; Flags
0x180031504  call    cs:__imp_RtlFreeHeap
0x18003150a  jmp     loc_18003136F
0x18003150f  mov     ebx, 0C0000017h
0x180031514  jmp     loc_180031491
0x180031519  mov     rcx, cs:WPP_GLOBAL_Control
0x180031520  test    byte ptr [rcx+1Ch], 40h
0x180031524  jz      loc_18003136A
0x18003152a  cmp     byte ptr [rcx+19h], 2
0x18003152e  jb      loc_18003136A
0x180031534  mov     edx, 10h
0x180031539  jmp     short loc_18003158D
0x18003153b  mov     ebx, 0C0000001h
0x180031540  jmp     loc_18003136F
0x180031545  lea     rax, [rbp+310h+P]
0x18003154c  cmp     rdi, rax
0x18003154f  jz      short loc_180031563
0x180031551  mov     rcx, cs:BipHeap; HeapHandle
0x180031558  mov     r8, rdi; P
0x18003155b  xor     edx, edx; Flags
0x18003155d  call    cs:__imp_RtlFreeHeap
0x180031563  mov     rcx, cs:BipHeap; HeapHandle
0x18003156a  xor     edx, edx; Flags
0x18003156c  movzx   r8d, si; Size
0x180031570  call    cs:__imp_RtlAllocateHeap
0x180031576  mov     rdi, rax
0x180031579  jmp     loc_180031467
0x18003157e  cmp     byte ptr [rcx+19h], 2
0x180031582  jb      loc_18003136A
0x180031588  mov     edx, 0Fh
0x18003158d  mov     rcx, [rcx+10h]
0x180031591  lea     r8, WPP_1ffc61b1bad13c8996c8de60b3700ee4_Traceguids
0x180031598  call    WPP_SF_
0x18003159d  jmp     loc_18003136A
```
