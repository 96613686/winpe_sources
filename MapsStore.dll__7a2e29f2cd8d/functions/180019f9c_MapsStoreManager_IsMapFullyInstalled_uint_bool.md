# MapsStoreManager::IsMapFullyInstalled(uint,bool *)

- ea: `0x180019f9c`
- end: `0x18001a04e`
- name: `?IsMapFullyInstalled@MapsStoreManager@@QEAAJIPEA_N@Z`
- size: `178`
- prototype: `__int64 __fastcall(MapsStoreManager *__hidden this, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180011aa0`

## callees

- `0x1800188dc`
- `0x180019f9c`
- `0x18001abe8`
- `0x18001af80`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x180019fd3`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180019fd3`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180019ff8`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180019ff8`

## string_xrefs

- `0x180019fc7`: `MapsStoreManager::IsMapFullyInstalled`
- `0x180019fef`: `MapsStoreManager::IsMapFullyInstalled`

## pseudocode

```c
__int64 __fastcall MapsStoreManager::IsMapFullyInstalled(MapsStoreManager *this, int a2, bool *a3)
{
  __int64 v4; // rsi
  unsigned int v7; // ecx
  int v8; // eax
  int v9; // r8d
  wil *v10; // rcx
  int v12; // eax

  v4 = a2;
  if ( a3 )
  {
    v8 = MapsStoreManager::EnsureReadyForOperation(this);
    if ( v8 >= 0 )
    {
      try
      {
        *((_QWORD *)this + 65) = v4;
        MapsStoreManager::StartNonInstallOperation(this, 4);
      }
      catch ( ... )
      {
        v12 = wil::ResultFromCaughtException(v10);
        return (unsigned int)ZTraceReportOrigination(v12, "MapsStoreManager::IsMapFullyInstalled", 567, this);
      }
      v8 = MapsStoreManager::WaitStoreOperation(this, 0xFFFFFFFF);
      if ( v8 >= 0 )
      {
        v7 = 0;
        *a3 = *((_BYTE *)this + 528);
        return v7;
      }
      v9 = 572;
    }
    else
    {
      v9 = 558;
    }
    return (unsigned int)ZTraceReportPropagation(v8, "MapsStoreManager::IsMapFullyInstalled", v9, this);
  }
  else
  {
    return (unsigned int)ZTraceReportOrigination(-2147467261, "MapsStoreManager::IsMapFullyInstalled", 556, this);
  }
}

```

## disassembly

```asm
0x180019f9c  mov     [rsp+arg_8], rbx
0x180019fa1  mov     [rsp+arg_18], rsi
0x180019fa6  mov     [rsp+arg_0], rcx
0x180019fab  push    rdi
0x180019fac  sub     rsp, 20h
0x180019fb0  mov     rdi, r8
0x180019fb3  movsxd  rsi, edx
0x180019fb6  mov     rbx, rcx
0x180019fb9  test    r8, r8
0x180019fbc  jnz     short loc_180019FDD
0x180019fbe  mov     r9, rcx
0x180019fc1  mov     r8d, 22Ch
0x180019fc7  lea     rdx, aMapsstoremanag_7; "MapsStoreManager::IsMapFullyInstalled"
0x180019fce  mov     ecx, 80004003h
0x180019fd3  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180019fd9  mov     ecx, eax; this
0x180019fdb  jmp     short loc_18001A03C
0x180019fdd  call    ?EnsureReadyForOperation@MapsStoreManager@@AEAAJXZ; MapsStoreManager::EnsureReadyForOperation(void)
0x180019fe2  test    eax, eax
0x180019fe4  jns     short loc_18001A000
0x180019fe6  mov     r8d, 22Eh
0x180019fec  mov     r9, rbx
0x180019fef  lea     rdx, aMapsstoremanag_7; "MapsStoreManager::IsMapFullyInstalled"
0x180019ff6  mov     ecx, eax
0x180019ff8  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180019ffe  jmp     short loc_180019FD9
0x18001a000  mov     [rbx+208h], rsi
0x18001a007  mov     edx, 4
0x18001a00c  mov     rcx, rbx
0x18001a00f  call    ?StartNonInstallOperation@MapsStoreManager@@AEAAXW4OperationType@1@@Z; MapsStoreManager::StartNonInstallOperation(MapsStoreManager::OperationType)
0x18001a014  nop
0x18001a015  or      edx, 0FFFFFFFFh; unsigned int
0x18001a018  mov     rcx, rbx; this
0x18001a01b  call    ?WaitStoreOperation@MapsStoreManager@@QEAAJK@Z; MapsStoreManager::WaitStoreOperation(ulong)
0x18001a020  test    eax, eax
0x18001a022  jns     short loc_18001A02C
0x18001a024  mov     r8d, 23Ch
0x18001a02a  jmp     short loc_180019FEC
0x18001a02c  xor     ecx, ecx
0x18001a02e  mov     al, [rbx+210h]
0x18001a034  mov     [rdi], al
0x18001a036  jmp     short loc_18001A03C
0x18001a038  mov     ecx, [rsp+28h+arg_10]
0x18001a03c  mov     eax, ecx
0x18001a03e  mov     rbx, [rsp+28h+arg_8]
0x18001a043  mov     rsi, [rsp+28h+arg_18]
0x18001a048  add     rsp, 20h
0x18001a04c  pop     rdi
0x18001a04d  retn
```
