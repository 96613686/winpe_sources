# SetCostFlag(IBackgroundCopyJob *,ulong)

- ea: `0x14001050c`
- end: `0x1400105b5`
- name: `?SetCostFlag@@YAJPEAUIBackgroundCopyJob@@K@Z`
- size: `169`
- prototype: `__int64 __fastcall(struct IBackgroundCopyJob *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140010a2c`

## callees

- `0x14000740c`
- `0x14000904c`
- `0x14001050c`
- `0x14001c010`

## string_xrefs

- `0x14001054f`: `Failed to get IBackgroundCopyJob5 hr=0x%8x`

## pseudocode

```c
__int64 __fastcall SetCostFlag(struct IBackgroundCopyJob *a1, int a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v6; // [rsp+28h] [rbp-20h] BYREF
  __int128 v7; // [rsp+30h] [rbp-18h] BYREF

  v6 = 0;
  v3 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_e847030c_bbba_4657_af6d_484aa42bf1fe,
         &v6);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v7 = 0;
    LODWORD(v7) = a2;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v6 + 424LL))(v6, 1, &v7);
  }
  else
  {
    LogError(L"Failed to get IBackgroundCopyJob5 hr=0x%8x", (unsigned int)v3);
  }
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v6);
  return v4;
}

```

## disassembly

```asm
0x14001050c  mov     r11, rsp
0x14001050f  mov     [r11+8], rbx
0x140010513  mov     [r11+10h], rsi
0x140010517  push    rdi
0x140010518  sub     rsp, 40h
0x14001051c  mov     edi, edx
0x14001051e  mov     qword ptr [r11-20h], 0
0x140010526  lea     rsi, ??_7?$SmartPtr@UIBackgroundCopyJob5@@@@6B@; const SmartPtr<IBackgroundCopyJob5>::`vftable'
0x14001052d  mov     [r11-28h], rsi
0x140010531  mov     rax, [rcx]
0x140010534  lea     r8, [r11-20h]
0x140010538  lea     rdx, _GUID_e847030c_bbba_4657_af6d_484aa42bf1fe
0x14001053f  mov     rax, [rax]
0x140010542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010547  mov     ebx, eax
0x140010549  test    eax, eax
0x14001054b  jns     short loc_14001055D
0x14001054d  mov     edx, eax
0x14001054f  lea     rcx, aFailedToGetIba; "Failed to get IBackgroundCopyJob5 hr=0x"...
0x140010556  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14001055b  jmp     short loc_140010594
0x14001055d  xorps   xmm0, xmm0
0x140010560  movups  [rsp+48h+var_18], xmm0
0x140010565  mov     dword ptr [rsp+48h+var_18], edi
0x140010569  mov     rcx, [rsp+48h+var_20]
0x14001056e  movaps  xmm0, [rsp+48h+var_18]
0x140010573  movdqa  [rsp+48h+var_18], xmm0
0x140010579  mov     rax, [rcx]
0x14001057c  lea     r8, [rsp+48h+var_18]
0x140010581  mov     edx, 1
0x140010586  mov     rax, [rax+1A8h]
0x14001058d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010592  mov     ebx, eax
0x140010594  mov     [rsp+48h+var_28], rsi
0x140010599  lea     rcx, [rsp+48h+var_20]
0x14001059e  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x1400105a3  mov     eax, ebx
0x1400105a5  mov     rbx, [rsp+48h+arg_0]
0x1400105aa  mov     rsi, [rsp+48h+arg_8]
0x1400105af  add     rsp, 40h
0x1400105b3  pop     rdi
0x1400105b4  retn
```
