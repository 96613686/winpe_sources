# MapsStoreManager::InstallAsync(uint *,ulong,uint *,ulong)

- ea: `0x180019e20`
- end: `0x180019f33`
- name: `?InstallAsync@MapsStoreManager@@QEAAJPEAIK0K@Z`
- size: `275`
- prototype: `__int64 __usercall@<rax>(MapsStoreManager *__hidden this@<rcx>, unsigned int *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180011a70`

## callees

- `0x1800182cc`
- `0x1800188dc`
- `0x180019e20`
- `0x18001ac2c`
- `0x18001d9d4`
- `0x1800363cc`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x180019f1b`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180019f1b`

## string_xrefs

- `0x180019f12`: `MapsStoreManager::InstallAsync`

## pseudocode

```c
__int64 __fastcall MapsStoreManager::InstallAsync(
        MapsStoreManager *this,
        unsigned int *a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned int a5)
{
  __int64 v6; // rsi
  int v9; // eax
  int v10; // r8d
  unsigned int v11; // edi
  __int64 **v12; // rcx
  __int64 *v13; // rax
  int i; // esi
  __int64 **v15; // rcx
  __int64 *v16; // rax
  int v17; // esi
  wil *v18; // rcx
  int v20; // eax

  v6 = a3;
  v9 = MapsStoreManager::EnsureReadyForOperation(this);
  if ( v9 < 0 )
  {
    v10 = 479;
    return (unsigned int)ZTraceReportPropagation(v9, "MapsStoreManager::InstallAsync", v10, this);
  }
  v9 = Pal::MapsbtsvcProxy::ensureJob((__int64)&Pal::MapsbtsvcProxy::smInstance, (__int64)this + 48);
  if ( v9 < 0 )
  {
    v10 = 481;
    return (unsigned int)ZTraceReportPropagation(v9, "MapsStoreManager::InstallAsync", v10, this);
  }
  v11 = 0;
  try
  {
    std::list<unsigned int>::resize((char *)this + 488, v6);
    if ( (_DWORD)v6 )
    {
      v12 = (__int64 **)**((_QWORD **)this + 61);
      *((_DWORD *)v12 + 4) = *a2;
      v13 = *v12;
      for ( i = v6 - 1; i; --i )
      {
        *((_DWORD *)v13 + 4) = *++a2;
        v13 = (__int64 *)*v13;
      }
    }
    std::list<unsigned int>::resize((char *)this + 504, a5);
    if ( a5 )
    {
      v15 = (__int64 **)**((_QWORD **)this + 63);
      *((_DWORD *)v15 + 4) = *a4;
      v16 = *v15;
      v17 = a5 - 1;
      if ( a5 != 1 )
      {
        do
        {
          *((_DWORD *)v16 + 4) = *++a4;
          v16 = (__int64 *)*v16;
          --v17;
        }
        while ( v17 );
      }
    }
    MapsStoreManager::CancelGridRequestsAndWait(this);
    MapsStoreManager::StartOperation(this, 2);
  }
  catch ( ... )
  {
    v20 = wil::ResultFromCaughtException(v18);
    return (unsigned int)ZTraceReportOrigination(v20, "MapsStoreManager::InstallAsync", 499, this);
  }
  return v11;
}

```

## disassembly

```asm
0x180019e20  mov     [rsp+arg_0], rcx
0x180019e25  push    rbx
0x180019e26  push    rsi
0x180019e27  push    rdi
0x180019e28  push    r12
0x180019e2a  push    r14
0x180019e2c  push    r15
0x180019e2e  sub     rsp, 38h
0x180019e32  mov     r15, r9
0x180019e35  mov     esi, r8d
0x180019e38  mov     r14, rdx
0x180019e3b  mov     rbx, rcx
0x180019e3e  call    ?EnsureReadyForOperation@MapsStoreManager@@AEAAJXZ; MapsStoreManager::EnsureReadyForOperation(void)
0x180019e43  test    eax, eax
0x180019e45  jns     short loc_180019E52
0x180019e47  mov     r8d, 1DFh
0x180019e4d  jmp     loc_180019F0F
0x180019e52  lea     rdx, [rbx+30h]
0x180019e56  lea     rcx, ?smInstance@MapsbtsvcProxy@Pal@@0V12@A; Pal::MapsbtsvcProxy Pal::MapsbtsvcProxy::smInstance
0x180019e5d  call    ?ensureJob@MapsbtsvcProxy@Pal@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::MapsbtsvcProxy::ensureJob(std::wstring const &)
0x180019e62  test    eax, eax
0x180019e64  js      loc_180019F09
0x180019e6a  xor     edi, edi
0x180019e6c  lea     r12, [rbx+1E8h]
0x180019e73  mov     rdx, rsi
0x180019e76  mov     rcx, r12
0x180019e79  call    ?resize@?$list@IV?$allocator@I@std@@@std@@QEAAX_K@Z; std::list<uint>::resize(unsigned __int64)
0x180019e7e  test    esi, esi
0x180019e80  jz      short loc_180019EA9
0x180019e82  mov     rax, [r12]
0x180019e86  mov     rcx, [rax]
0x180019e89  mov     eax, [r14]
0x180019e8c  mov     [rcx+10h], eax
0x180019e8f  mov     rax, [rcx]
0x180019e92  sub     esi, 1
0x180019e95  jz      short loc_180019EA9
0x180019e97  lea     r14, [r14+4]
0x180019e9b  mov     ecx, [r14]
0x180019e9e  mov     [rax+10h], ecx
0x180019ea1  mov     rax, [rax]
0x180019ea4  add     esi, 0FFFFFFFFh
0x180019ea7  jnz     short loc_180019E97
0x180019ea9  lea     r14, [rbx+1F8h]
0x180019eb0  mov     esi, [rsp+68h+arg_20]
0x180019eb7  mov     edx, esi
0x180019eb9  mov     rcx, r14
0x180019ebc  call    ?resize@?$list@IV?$allocator@I@std@@@std@@QEAAX_K@Z; std::list<uint>::resize(unsigned __int64)
0x180019ec1  test    esi, esi
0x180019ec3  jz      short loc_180019EEB
0x180019ec5  mov     rax, [r14]
0x180019ec8  mov     rcx, [rax]
0x180019ecb  mov     eax, [r15]
0x180019ece  mov     [rcx+10h], eax
0x180019ed1  mov     rax, [rcx]
0x180019ed4  sub     esi, 1
0x180019ed7  jz      short loc_180019EEB
0x180019ed9  lea     r15, [r15+4]
0x180019edd  mov     ecx, [r15]
0x180019ee0  mov     [rax+10h], ecx
0x180019ee3  mov     rax, [rax]
0x180019ee6  add     esi, 0FFFFFFFFh
0x180019ee9  jnz     short loc_180019ED9
0x180019eeb  mov     rcx, rbx; this
0x180019eee  call    ?CancelGridRequestsAndWait@MapsStoreManager@@AEAAXXZ; MapsStoreManager::CancelGridRequestsAndWait(void)
0x180019ef3  mov     edx, 2
0x180019ef8  mov     rcx, rbx
0x180019efb  call    ?StartOperation@MapsStoreManager@@AEAAXW4OperationType@1@@Z; MapsStoreManager::StartOperation(MapsStoreManager::OperationType)
0x180019f00  nop
0x180019f01  jmp     short loc_180019F23
0x180019f03  mov     edi, [rsp+68h+var_48]
0x180019f07  jmp     short loc_180019F23
0x180019f09  mov     r8d, 1E1h
0x180019f0f  mov     r9, rbx
0x180019f12  lea     rdx, aMapsstoremanag_13; "MapsStoreManager::InstallAsync"
0x180019f19  mov     ecx, eax
0x180019f1b  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180019f21  mov     edi, eax
0x180019f23  mov     eax, edi
0x180019f25  add     rsp, 38h
0x180019f29  pop     r15
0x180019f2b  pop     r14
0x180019f2d  pop     r12
0x180019f2f  pop     rdi
0x180019f30  pop     rsi
0x180019f31  pop     rbx
0x180019f32  retn
```
