# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180015370`
- end: `0x18001544d`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015460`

## callees

- `0x180015370`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        __int64 *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v5; // eax

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == -1804115413
      && a2[1] == *(_DWORD *)&GUID_9477622b_1340_5574_81fc_5013581f57c9.Data2
      && a2[2] == *(_DWORD *)GUID_9477622b_1340_5574_81fc_5013581f57c9.Data4
      && a2[3] == *(_DWORD *)&GUID_9477622b_1340_5574_81fc_5013581f57c9.Data4[4] )
    {
      *a3 = a1;
LABEL_22:
      a1 = *a3;
      goto LABEL_6;
    }
LABEL_12:
    v4 = a1 + 8;
    if ( *a2 == -1796592748 )
    {
      if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
        || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
    }
    else
    {
      if ( *a2 != 3
        || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
        || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
    }
    if ( a2[3] == v5 )
    {
      *a3 = v4;
      goto LABEL_22;
    }
    return (unsigned int)-2147467262;
  }
  if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_12;
  }
  *a3 = a1;
LABEL_6:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x180015370  push    rbx
0x180015372  sub     rsp, 20h
0x180015376  xor     ebx, ebx
0x180015378  mov     [r8], rbx
0x18001537b  cmp     [rdx], ebx
0x18001537d  jnz     short loc_1800153B4
0x18001537f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180015385  cmp     [rdx+4], eax
0x180015388  jnz     short loc_1800153E2
0x18001538a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180015390  cmp     [rdx+8], eax
0x180015393  jnz     short loc_1800153E2
0x180015395  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18001539b  cmp     [rdx+0Ch], eax
0x18001539e  jnz     short loc_1800153E2
0x1800153a0  mov     [r8], rcx
0x1800153a3  mov     rax, [rcx]
0x1800153a6  mov     rax, [rax+8]
0x1800153aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153af  jmp     loc_180015445
0x1800153b4  cmp     dword ptr [rdx], 9477622Bh
0x1800153ba  jnz     short loc_1800153E2
0x1800153bc  mov     eax, dword ptr cs:_GUID_9477622b_1340_5574_81fc_5013581f57c9.Data2
0x1800153c2  cmp     [rdx+4], eax
0x1800153c5  jnz     short loc_1800153E2
0x1800153c7  mov     eax, dword ptr cs:_GUID_9477622b_1340_5574_81fc_5013581f57c9.Data4
0x1800153cd  cmp     [rdx+8], eax
0x1800153d0  jnz     short loc_1800153E2
0x1800153d2  mov     eax, dword ptr cs:_GUID_9477622b_1340_5574_81fc_5013581f57c9.Data4+4
0x1800153d8  cmp     [rdx+0Ch], eax
0x1800153db  jnz     short loc_1800153E2
0x1800153dd  mov     [r8], rcx
0x1800153e0  jmp     short loc_180015438
0x1800153e2  add     rcx, 8
0x1800153e6  cmp     dword ptr [rdx], 94EA2B94h
0x1800153ec  jnz     short loc_18001540C
0x1800153ee  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x1800153f4  cmp     [rdx+4], eax
0x1800153f7  jnz     short loc_180015440
0x1800153f9  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x1800153ff  cmp     [rdx+8], eax
0x180015402  jnz     short loc_180015440
0x180015404  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18001540a  jmp     short loc_18001542D
0x18001540c  cmp     dword ptr [rdx], 3
0x18001540f  jnz     short loc_180015440
0x180015411  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x180015417  cmp     [rdx+4], eax
0x18001541a  jnz     short loc_180015440
0x18001541c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x180015422  cmp     [rdx+8], eax
0x180015425  jnz     short loc_180015440
0x180015427  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18001542d  cmp     [rdx+0Ch], eax
0x180015430  jnz     short loc_180015440
0x180015432  mov     rax, r8
0x180015435  mov     [rax], rcx
0x180015438  mov     rcx, [r8]
0x18001543b  jmp     loc_1800153A3
0x180015440  mov     ebx, 80004002h
0x180015445  mov     eax, ebx
0x180015447  add     rsp, 20h
0x18001544b  pop     rbx
0x18001544c  retn
```
