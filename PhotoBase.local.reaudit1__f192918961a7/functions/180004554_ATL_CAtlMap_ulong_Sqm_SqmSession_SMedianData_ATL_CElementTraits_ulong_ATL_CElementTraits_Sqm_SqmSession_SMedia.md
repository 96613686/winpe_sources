# ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::InitHashTable(uint,bool)

- ea: `0x180004554`
- end: `0x1800045ee`
- name: `?InitHashTable@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@QEAA_NI_N@Z`
- size: `154`
- prototype: ``
- caller_count: `12`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180005744`
- `0x180005874`
- `0x1800059a4`
- `0x180005ad4`
- `0x180005c54`
- `0x180005d14`
- `0x180005dd4`
- `0x180005e94`
- `0x1800062bc`
- `0x180006388`
- `0x180006880`
- `0x1800069e4`

## callees

- `0x180002172`
- `0x180002650`
- `0x180004554`
- `0x180006ce8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004574`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004574`

## pseudocode

```c
char __fastcall ATL::CAtlMap<unsigned long,Sqm::SqmSession::SMedianData,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::InitHashTable(
        void **a1,
        unsigned int a2,
        bool a3)
{
  unsigned __int64 v4; // rdi
  __int64 v5; // rbx
  void *v6; // rcx
  unsigned __int64 v7; // rsi
  unsigned __int128 v8; // rax
  unsigned __int64 v12; // [rsp+58h] [rbp+20h]

  v4 = a2;
  v5 = (__int64)a1;
  v6 = *a1;
  if ( v6 )
  {
    free(v6);
    *(_QWORD *)v5 = 0;
  }
  if ( a3 )
  {
    v7 = v4;
    v12 = v4;
    v8 = v4 * (unsigned __int128)8uLL;
    if ( !is_mul_ok(v4, 8u) )
      *(_QWORD *)&v8 = -1;
    try
    {
      BYTE8(v8) = 1;
      *(_QWORD *)v5 = BasePrivate::New(v8, *((unsigned __int64 *)&v8 + 1), a3);
    }
    catch ( ... )
    {
      v5 = (__int64)a1;
      LODWORD(v4) = a2;
      v7 = v12;
    }
    if ( !*(_QWORD *)v5 )
      return 0;
    memset_0(*(void **)v5, 0, 8 * v7);
  }
  *(_DWORD *)(v5 + 16) = v4;
  ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::UpdateRehashThresholds(v5);
  return 1;
}

```

## disassembly

```asm
0x180004554  mov     [rsp+arg_8], edx
0x180004558  mov     [rsp+arg_0], rcx
0x18000455d  push    rbx
0x18000455e  push    rsi
0x18000455f  push    rdi
0x180004560  sub     rsp, 20h
0x180004564  mov     sil, r8b
0x180004567  mov     edi, edx
0x180004569  mov     rbx, rcx
0x18000456c  mov     rcx, [rcx]; Block
0x18000456f  test    rcx, rcx
0x180004572  jz      short loc_180004581
0x180004574  call    cs:__imp_free
0x18000457a  mov     qword ptr [rbx], 0
0x180004581  test    sil, sil
0x180004584  jz      short loc_1800045D9
0x180004586  mov     rsi, rdi
0x180004589  mov     [rsp+38h+arg_18], rdi
0x18000458e  mov     eax, 8
0x180004593  mul     rsi
0x180004596  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000459d  cmovb   rax, rcx
0x1800045a1  mov     dl, 1; unsigned __int64
0x1800045a3  mov     rcx, rax; Size
0x1800045a6  call    ?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x1800045ab  mov     [rbx], rax
0x1800045ae  jmp     short loc_1800045BE
0x1800045b0  mov     rbx, [rsp+38h+arg_0]
0x1800045b5  mov     edi, [rsp+38h+arg_8]
0x1800045b9  mov     rsi, [rsp+38h+arg_18]
0x1800045be  mov     rcx, [rbx]; void *
0x1800045c1  test    rcx, rcx
0x1800045c4  jnz     short loc_1800045CA
0x1800045c6  xor     al, al
0x1800045c8  jmp     short loc_1800045E6
0x1800045ca  lea     r8, ds:0[rsi*8]; Size
0x1800045d2  xor     edx, edx; Val
0x1800045d4  call    memset_0
0x1800045d9  mov     [rbx+10h], edi
0x1800045dc  mov     rcx, rbx
0x1800045df  call    ?UpdateRehashThresholds@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEAAXXZ; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::UpdateRehashThresholds(void)
0x1800045e4  mov     al, 1
0x1800045e6  add     rsp, 20h
0x1800045ea  pop     rdi
0x1800045eb  pop     rsi
0x1800045ec  pop     rbx
0x1800045ed  retn
```
