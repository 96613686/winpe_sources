# StartAddress

- ea: `0x140016440`
- end: `0x1400165ab`
- name: `StartAddress`
- size: `363`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400083f0`
- `0x1400143fc`
- `0x140015d10`
- `0x140016440`
- `0x140017cd4`
- `0x14005c580`

## import_xrefs

- `KERNEL32!Sleep` at `0x140016532`
- `KERNEL32!Sleep` at `0x140016532`
- `KERNEL32!GetThreadIOPendingFlag` at `0x14001651d`
- `KERNEL32!GetThreadIOPendingFlag` at `0x14001651d`
- `KERNEL32!GetCurrentThread` at `0x140016510`
- `KERNEL32!GetCurrentThread` at `0x140016510`
- `ADVAPI32!RevertToSelf` at `0x140016487`
- `ADVAPI32!RevertToSelf` at `0x140016487`

## pseudocode

```c
__int64 __fastcall StartAddress(volatile signed __int32 *lpThreadParameter)
{
  volatile signed __int32 *v1; // rbx
  signed __int64 v2; // rax
  signed __int64 v3; // rtt
  HANDLE CurrentThread; // rax
  _QWORD *v5; // rdi
  __int64 v6; // rcx
  __int128 v8; // [rsp+20h] [rbp-40h] BYREF
  __int64 v9; // [rsp+30h] [rbp-30h]
  int v10; // [rsp+40h] [rbp-20h]
  __int64 v11; // [rsp+48h] [rbp-18h]
  __int64 v12; // [rsp+50h] [rbp-10h]
  int v13; // [rsp+58h] [rbp-8h]
  BOOL IOIsPending; // [rsp+70h] [rbp+10h] BYREF
  signed __int64 v15; // [rsp+78h] [rbp+18h]

  v1 = lpThreadParameter;
  _InterlockedIncrement(lpThreadParameter + 6);
  v12 = 0;
  v10 = 0;
  v8 = 0;
  v9 = 0;
  v11 = 0;
  v13 = 0;
  if ( RevertToSelf() && (unsigned __int8)sub_140017CD4(*((_QWORD *)v1 + 1), &v8) )
  {
    *(_QWORD *)&v8 = v1;
    while ( (unsigned int)sub_140015D10((__int64)v1, &v8) )
      v1 = (volatile signed __int32 *)v8;
    *(_QWORD *)&v8 = 0;
  }
  else
  {
    sub_1400083F0(507553762);
    _m_prefetchw((const void *)(v1 + 4));
    v2 = *((_QWORD *)v1 + 2);
    do
    {
      HIDWORD(v15) = HIDWORD(v2);
      LODWORD(v15) = v2 & 0xC007FFFF | (((((unsigned int)v2 >> 19) - 1) & 0x7FF) << 19);
      v3 = v2;
      v2 = _InterlockedCompareExchange64((volatile signed __int64 *)v1 + 2, v15, v2);
    }
    while ( v3 != v2 );
  }
  sub_140017CD4(*((_QWORD *)v1 + 1), 0);
  IOIsPending = 0;
  while ( (v1[4] & 0x40000000) == 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( !GetThreadIOPendingFlag(CurrentThread, &IOIsPending) || !IOIsPending )
      break;
    Sleep(1u);
  }
  if ( !(_DWORD)v12 )
    sub_1400143FC(&v8, 0);
  v5 = **(_QWORD ***)(*((_QWORD *)v1 + 1) + 336LL);
  while ( v5 )
  {
    v6 = v5[3];
    v5 = (_QWORD *)*v5;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
  }
  _InterlockedDecrement(v1 + 6);
  return 0;
}

```

## disassembly

```asm
0x140016440  mov     [rsp-8+arg_10], rbx
0x140016445  mov     [rsp-8+arg_18], rdi
0x14001644a  push    rbp
0x14001644b  mov     rbp, rsp
0x14001644e  sub     rsp, 60h
0x140016452  mov     rbx, rcx
0x140016455  lock inc dword ptr [rcx+18h]
0x140016459  mov     [rbp+var_10], 0
0x140016461  mov     [rbp+var_20], 0
0x140016468  xorps   xmm0, xmm0
0x14001646b  movdqa  [rbp+var_40], xmm0
0x140016470  mov     [rbp+var_30], 0
0x140016478  mov     [rbp+var_18], 0
0x140016480  mov     [rbp+var_8], 0
0x140016487  call    cs:RevertToSelf
0x14001648d  test    eax, eax
0x14001648f  jz      loc_140016593
0x140016495  lea     rdx, [rbp+var_40]
0x140016499  mov     rcx, [rbx+8]
0x14001649d  call    sub_140017CD4
0x1400164a2  test    al, al
0x1400164a4  jz      loc_140016593
0x1400164aa  mov     qword ptr [rbp+var_40], rbx
0x1400164ae  jmp     short loc_1400164B4
0x1400164b0  mov     rbx, qword ptr [rbp+var_40]
0x1400164b4  lea     rdx, [rbp+var_40]
0x1400164b8  mov     rcx, rbx
0x1400164bb  call    sub_140015D10
0x1400164c0  test    eax, eax
0x1400164c2  jnz     short loc_1400164B0
0x1400164c4  mov     qword ptr [rbp+var_40], 0
0x1400164cc  jmp     short loc_1400164FC
0x1400164ce  mov     [rbp+arg_8], rax
0x1400164d2  mov     ecx, dword ptr [rbp+arg_8]
0x1400164d5  mov     edx, ecx
0x1400164d7  shr     edx, 13h
0x1400164da  dec     edx
0x1400164dc  and     edx, 7FFh
0x1400164e2  shl     edx, 13h
0x1400164e5  and     ecx, 0C007FFFFh
0x1400164eb  or      edx, ecx
0x1400164ed  mov     dword ptr [rbp+arg_8], edx
0x1400164f0  mov     rcx, [rbp+arg_8]
0x1400164f4  lock cmpxchg [rbx+10h], rcx
0x1400164fa  jnz     short loc_1400164CE
0x1400164fc  xor     edx, edx
0x1400164fe  mov     rcx, [rbx+8]
0x140016502  call    sub_140017CD4
0x140016507  mov     [rbp+IOIsPending], 0
0x14001650e  jmp     short loc_140016538
0x140016510  call    cs:GetCurrentThread
0x140016516  mov     rcx, rax; hThread
0x140016519  lea     rdx, [rbp+IOIsPending]; lpIOIsPending
0x14001651d  call    cs:GetThreadIOPendingFlag
0x140016523  test    eax, eax
0x140016525  jz      short loc_140016541
0x140016527  cmp     [rbp+IOIsPending], 0
0x14001652b  jz      short loc_140016541
0x14001652d  mov     ecx, 1; dwMilliseconds
0x140016532  call    cs:Sleep
0x140016538  mov     eax, [rbx+10h]
0x14001653b  bt      eax, 1Eh
0x14001653f  jnb     short loc_140016510
0x140016541  cmp     dword ptr [rbp+var_10], 0
0x140016545  jnz     short loc_140016552
0x140016547  xor     edx, edx
0x140016549  lea     rcx, [rbp+var_40]
0x14001654d  call    sub_1400143FC
0x140016552  mov     rax, [rbx+8]
0x140016556  mov     rcx, [rax+150h]
0x14001655d  mov     rdi, [rcx]
0x140016560  jmp     short loc_140016576
0x140016562  mov     rcx, [rdi+18h]
0x140016566  mov     rdi, [rdi]
0x140016569  mov     rax, [rcx]
0x14001656c  mov     rax, [rax+18h]
0x140016570  call    cs:__guard_dispatch_icall_fptr
0x140016576  test    rdi, rdi
0x140016579  jnz     short loc_140016562
0x14001657b  lock dec dword ptr [rbx+18h]
0x14001657f  xor     eax, eax
0x140016581  lea     r11, [rsp+60h+var_s0]
0x140016586  mov     rbx, [r11+20h]
0x14001658a  mov     rdi, [r11+28h]
0x14001658e  mov     rsp, r11
0x140016591  pop     rbp
0x140016592  retn
0x140016593  mov     ecx, 1E40A7E2h
0x140016598  call    sub_1400083F0
0x14001659d  prefetchw byte ptr [rbx+10h]
0x1400165a1  mov     rax, [rbx+10h]
0x1400165a5  jmp     loc_1400164CE
```
