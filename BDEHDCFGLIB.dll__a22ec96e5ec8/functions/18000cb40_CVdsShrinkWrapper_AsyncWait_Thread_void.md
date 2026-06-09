# CVdsShrinkWrapper::AsyncWait_Thread(void *)

- ea: `0x18000cb40`
- end: `0x18000cc2f`
- name: `?AsyncWait_Thread@CVdsShrinkWrapper@@CAXPEAX@Z`
- size: `239`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800010e4`
- `0x18000cb40`
- `0x180015010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000cbc6`
- `KERNEL32!SetEvent` at `0x18000cbc6`
- `KERNEL32!CloseHandle` at `0x18000cc03`
- `KERNEL32!CloseHandle` at `0x180014117`
- `KERNEL32!CloseHandle` at `0x18000cc03`
- `KERNEL32!CloseHandle` at `0x180014117`
- `ole32!CoInitializeEx` at `0x18000cb70`
- `ole32!CoInitializeEx` at `0x18000cb70`
- `ole32!CoUninitialize` at `0x18000cc1e`
- `ole32!CoUninitialize` at `0x180014134`
- `ole32!CoUninitialize` at `0x18000cc1e`
- `ole32!CoUninitialize` at `0x180014134`

## pseudocode

```c
void __fastcall CVdsShrinkWrapper::AsyncWait_Thread(_QWORD *a1)
{
  char v2; // di
  void *v3; // rcx
  __int128 v4; // [rsp+28h] [rbp-30h] BYREF
  __int128 v5; // [rsp+38h] [rbp-20h]
  int v6; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  v6 = 0;
  v4 = 0;
  v5 = 0;
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    v2 = 1;
    (*(void (__fastcall **)(_QWORD, int *, __int128 *))(*(_QWORD *)*a1 + 32LL))(*a1, &v6, &v4);
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)a1 + 14, 2, 0) )
    {
      *((_DWORD *)a1 + 2) = v6;
      *((_OWORD *)a1 + 1) = v4;
      *((_OWORD *)a1 + 2) = v5;
      SetEvent((HANDLE)a1[6]);
    }
  }
  if ( a1 && _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 15, 0xFFFFFFFF) == 1 )
  {
    if ( *a1 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
      *a1 = 0;
    }
    v3 = (void *)a1[6];
    if ( v3 )
    {
      CloseHandle(v3);
      a1[6] = 0;
    }
    operator delete(a1);
  }
  if ( v2 )
    CoUninitialize();
}

```

## disassembly

```asm
0x18000cb40  mov     rax, rsp
0x18000cb43  mov     [rax+18h], rbx
0x18000cb47  mov     [rax+8], rcx
0x18000cb4b  push    rdi
0x18000cb4c  sub     rsp, 50h
0x18000cb50  mov     rbx, rcx
0x18000cb53  xor     dil, dil
0x18000cb56  mov     [rax-38h], dil
0x18000cb5a  mov     dword ptr [rax+10h], 0
0x18000cb61  xorps   xmm0, xmm0
0x18000cb64  movups  xmmword ptr [rax-30h], xmm0
0x18000cb68  movups  xmmword ptr [rax-20h], xmm0
0x18000cb6c  xor     edx, edx; dwCoInit
0x18000cb6e  xor     ecx, ecx; pvReserved
0x18000cb70  call    cs:__imp_CoInitializeEx
0x18000cb76  test    eax, eax
0x18000cb78  js      short loc_18000CBCD
0x18000cb7a  mov     dil, 1
0x18000cb7d  mov     [rsp+58h+var_38], dil
0x18000cb82  mov     rcx, [rbx]
0x18000cb85  mov     rax, [rcx]
0x18000cb88  lea     r8, [rsp+58h+var_30]
0x18000cb8d  lea     rdx, [rsp+58h+arg_8]
0x18000cb92  mov     rax, [rax+20h]
0x18000cb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb9b  mov     ecx, 2
0x18000cba0  xor     eax, eax
0x18000cba2  lock cmpxchg [rbx+38h], ecx
0x18000cba7  jnz     short loc_18000CBCD
0x18000cba9  mov     eax, [rsp+58h+arg_8]
0x18000cbad  mov     [rbx+8], eax
0x18000cbb0  movups  xmm0, [rsp+58h+var_30]
0x18000cbb5  movups  xmmword ptr [rbx+10h], xmm0
0x18000cbb9  movups  xmm1, [rsp+58h+var_20]
0x18000cbbe  movups  xmmword ptr [rbx+20h], xmm1
0x18000cbc2  mov     rcx, [rbx+30h]; hEvent
0x18000cbc6  call    cs:__imp_SetEvent
0x18000cbcc  nop
0x18000cbcd  test    rbx, rbx
0x18000cbd0  jz      short loc_18000CC19
0x18000cbd2  or      eax, 0FFFFFFFFh
0x18000cbd5  lock xadd [rbx+3Ch], eax
0x18000cbda  cmp     eax, 1
0x18000cbdd  jnz     short loc_18000CC19
0x18000cbdf  mov     rcx, [rbx]
0x18000cbe2  test    rcx, rcx
0x18000cbe5  jz      short loc_18000CBFA
0x18000cbe7  mov     rax, [rcx]
0x18000cbea  mov     rax, [rax+10h]
0x18000cbee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbf3  mov     qword ptr [rbx], 0
0x18000cbfa  mov     rcx, [rbx+30h]; hObject
0x18000cbfe  test    rcx, rcx
0x18000cc01  jz      short loc_18000CC11
0x18000cc03  call    cs:__imp_CloseHandle
0x18000cc09  mov     qword ptr [rbx+30h], 0
0x18000cc11  mov     rcx, rbx; Block
0x18000cc14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cc19  test    dil, dil
0x18000cc1c  jz      short loc_18000CC24
0x18000cc1e  call    cs:__imp_CoUninitialize
0x18000cc24  mov     rbx, [rsp+58h+arg_10]
0x18000cc29  add     rsp, 50h
0x18000cc2d  pop     rdi
0x18000cc2e  retn
0x1800140cd  push    rbx
0x1800140cf  push    rbp
0x1800140d0  sub     rsp, 28h
0x1800140d4  mov     rbp, rdx
0x1800140d7  mov     rbx, [rbp+60h]
0x1800140db  test    rbx, rbx
0x1800140de  jz      short loc_18001412E
0x1800140e0  or      eax, 0FFFFFFFFh
0x1800140e3  lock xadd [rbx+3Ch], eax
0x1800140e8  cmp     eax, 1
0x1800140eb  jnz     short loc_18001412E
0x1800140ed  cmp     qword ptr [rbx], 0
0x1800140f1  jz      short loc_18001410C
0x1800140f3  mov     rax, [rbx]
0x1800140f6  mov     rcx, [rax]
0x1800140f9  mov     rax, [rcx+10h]
0x1800140fd  mov     rcx, [rbx]
0x180014100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014105  mov     qword ptr [rbx], 0
0x18001410c  cmp     qword ptr [rbx+30h], 0
0x180014111  jz      short loc_180014125
0x180014113  mov     rcx, [rbx+30h]; hObject
0x180014117  call    cs:__imp_CloseHandle
0x18001411d  mov     qword ptr [rbx+30h], 0
0x180014125  mov     rcx, rbx; Block
0x180014128  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001412d  nop
0x18001412e  cmp     byte ptr [rbp+20h], 0
0x180014132  jz      short loc_18001413B
0x180014134  call    cs:__imp_CoUninitialize
0x18001413a  nop
0x18001413b  add     rsp, 28h
0x18001413f  pop     rbp
0x180014140  pop     rbx
0x180014141  retn
```
