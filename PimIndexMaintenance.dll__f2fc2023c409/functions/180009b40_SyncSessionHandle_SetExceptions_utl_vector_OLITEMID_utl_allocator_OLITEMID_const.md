# SyncSessionHandle::SetExceptions(utl::vector<OLITEMID,utl::allocator<OLITEMID>> const &)

- ea: `0x180009b40`
- end: `0x180009c41`
- name: `?SetExceptions@SyncSessionHandle@@QEAAJAEBV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@@Z`
- size: `257`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000523c`

## callees

- `0x180002da8`
- `0x1800067c0`
- `0x1800086a0`
- `0x180009b40`
- `0x18000c5b8`
- `0x180022010`

## string_xrefs

- `0x180009b5b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180009b76`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180009c1e`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall SyncSessionHandle::SetExceptions(_DWORD *a1, _QWORD *a2)
{
  __int64 v4; // rcx
  void *v6; // rax
  unsigned __int64 i; // rbx
  int v8; // eax
  unsigned int v9; // esi
  unsigned __int64 v10; // [rsp+60h] [rbp+8h] BYREF

  if ( a1[8] )
  {
    v10 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(a2[1] - *a2) >> 2);
    if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
    {
      v6 = _t_address();
      EtwTraceMessage(&ETWMESSAGE, v6, &v10);
    }
    for ( i = 0; i < v10; ++i )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int64))(**(_QWORD **)a1 + 144LL))(
             *(_QWORD *)a1,
             0,
             12,
             *a2 + 12 * i);
      v9 = v8;
      if ( v8 < 0 )
      {
        Log_HREvent(
          (unsigned int)v8,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
          180);
        return v9;
      }
    }
    return 0;
  }
  else
  {
    Log_HREvent(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      168);
    Log_AssertionEvent(
      v4,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      168);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180009b40  push    rbx
0x180009b42  push    rsi
0x180009b43  push    rdi
0x180009b44  push    r14
0x180009b46  sub     rsp, 38h
0x180009b4a  cmp     dword ptr [rcx+20h], 0
0x180009b4e  mov     rdi, rdx
0x180009b51  mov     r14, rcx
0x180009b54  jnz     short loc_180009B89
0x180009b56  mov     edi, 0A8h
0x180009b5b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009b62  mov     ebx, 80070057h
0x180009b67  mov     r9d, edi
0x180009b6a  mov     ecx, ebx
0x180009b6c  xor     edx, edx
0x180009b6e  call    Log_HREvent
0x180009b73  mov     r8d, edi
0x180009b76  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009b7d  call    Log_AssertionEvent
0x180009b82  mov     eax, ebx
0x180009b84  jmp     loc_180009C37
0x180009b89  mov     rax, [rdx+8]
0x180009b8d  mov     rcx, 0AAAAAAAAAAAAAAABh
0x180009b97  sub     rax, [rdx]
0x180009b9a  mov     r9d, 4
0x180009ba0  sar     rax, 2
0x180009ba4  imul    rax, rcx
0x180009ba8  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, r9b
0x180009baf  mov     [rsp+58h+arg_0], rax
0x180009bb4  jz      short loc_180009BE1
0x180009bb6  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x180009bbb  mov     rdx, rax; void *
0x180009bbe  mov     [rsp+58h+var_30], 0FFFFFFFFFFFFFFFFh
0x180009bc7  lea     r8, [rsp+58h+arg_0]
0x180009bcc  mov     [rsp+58h+var_38], 0
0x180009bd5  lea     rcx, _ETWMESSAGE; EventDescriptor
0x180009bdc  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x180009be1  xor     ebx, ebx
0x180009be3  cmp     rbx, [rsp+58h+arg_0]
0x180009be8  jnb     short loc_180009C35
0x180009bea  mov     rax, [rdi]
0x180009bed  lea     rdx, [rbx+rbx*2]
0x180009bf1  mov     rcx, [r14]
0x180009bf4  lea     r9, [rax+rdx*4]
0x180009bf8  xor     edx, edx
0x180009bfa  mov     r8, [rcx]
0x180009bfd  mov     rax, [r8+90h]
0x180009c04  lea     r8d, [rdx+0Ch]
0x180009c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c0d  mov     esi, eax
0x180009c0f  test    eax, eax
0x180009c11  js      short loc_180009C18
0x180009c13  inc     rbx
0x180009c16  jmp     short loc_180009BE3
0x180009c18  mov     r9d, 0B4h
0x180009c1e  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009c25  mov     edx, 1
0x180009c2a  mov     ecx, esi
0x180009c2c  call    Log_HREvent
0x180009c31  mov     eax, esi
0x180009c33  jmp     short loc_180009C37
0x180009c35  xor     eax, eax
0x180009c37  add     rsp, 38h
0x180009c3b  pop     r14
0x180009c3d  pop     rdi
0x180009c3e  pop     rsi
0x180009c3f  pop     rbx
0x180009c40  retn
```
