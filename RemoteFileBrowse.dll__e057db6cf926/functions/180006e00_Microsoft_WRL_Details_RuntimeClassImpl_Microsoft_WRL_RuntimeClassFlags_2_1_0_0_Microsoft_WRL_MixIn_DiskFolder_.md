# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::MixIn<DiskFolder,RfbShellFolderBase,1>,IResolveShellLink>::QueryInterface(_GUID const &,void * *)

- ea: `0x180006e00`
- end: `0x180006ec9`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$MixIn@VDiskFolder@@VRfbShellFolderBase@@$00@23@UIResolveShellLink@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `201`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006ed0`

## callees

- `0x180005cb0`
- `0x180006e00`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::MixIn<DiskFolder,RfbShellFolderBase,1>,IResolveShellLink>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  int CanCastTo; // ebx
  _QWORD *v5; // r8
  _DWORD *v6; // r9
  __int64 v7; // r10

  *a3 = 0;
  if ( !*a2
    && a2[1] == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    && a2[2] == *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    && a2[3] == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    v3 = (a1 + 16) & -(__int64)(a1 != 0);
    *a3 = v3;
    (*(void (__fastcall **)(__int64, _DWORD *, __int64 *, _DWORD *))(*(_QWORD *)v3 + 8LL))(v3, a2, a3, a2);
    return 0;
  }
  else
  {
    CanCastTo = Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IPersistIDList>::CanCastTo(
                  (a1 + 16) & -(__int64)(a1 != 0),
                  a2);
    if ( CanCastTo < 0 )
    {
      if ( *v6 != 1557473667
        || v6[1] != *(_DWORD *)&GUID_5cd52983_9449_11d2_963a_00c04f79adf0.Data2
        || v6[2] != *(_DWORD *)GUID_5cd52983_9449_11d2_963a_00c04f79adf0.Data4
        || v6[3] != *(_DWORD *)&GUID_5cd52983_9449_11d2_963a_00c04f79adf0.Data4[4] )
      {
        return (unsigned int)-2147467262;
      }
      *v5 = v7;
      CanCastTo = 0;
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  }
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x180006e00  push    rbx
0x180006e02  sub     rsp, 20h
0x180006e06  mov     r9, rdx
0x180006e09  mov     r10, rcx
0x180006e0c  mov     qword ptr [r8], 0
0x180006e13  cmp     dword ptr [rdx], 0
0x180006e16  jnz     short loc_180006E59
0x180006e18  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180006e1e  cmp     [rdx+4], eax
0x180006e21  jnz     short loc_180006E59
0x180006e23  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180006e29  cmp     [rdx+8], eax
0x180006e2c  jnz     short loc_180006E59
0x180006e2e  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x180006e34  cmp     [rdx+0Ch], eax
0x180006e37  jnz     short loc_180006E59
0x180006e39  lea     rax, [rcx+10h]
0x180006e3d  neg     r10
0x180006e40  sbb     rcx, rcx
0x180006e43  and     rcx, rax
0x180006e46  mov     [r8], rcx
0x180006e49  mov     rax, [rcx]
0x180006e4c  mov     rax, [rax+8]
0x180006e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e55  xor     ebx, ebx
0x180006e57  jmp     short loc_180006EB9
0x180006e59  mov     rax, r10
0x180006e5c  lea     rdx, [rcx+10h]
0x180006e60  neg     rax
0x180006e63  sbb     rcx, rcx
0x180006e66  and     rcx, rdx
0x180006e69  mov     rdx, r9
0x180006e6c  call    ?CanCastTo@?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIPersistIDList@@@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IPersistIDList>::CanCastTo(_GUID const &,void * *)
0x180006e71  mov     ebx, eax
0x180006e73  test    eax, eax
0x180006e75  jns     short loc_180006EA9
0x180006e77  cmp     dword ptr [r9], 5CD52983h
0x180006e7e  jnz     short loc_180006EC1
0x180006e80  mov     eax, dword ptr cs:_GUID_5cd52983_9449_11d2_963a_00c04f79adf0.Data2
0x180006e86  cmp     [r9+4], eax
0x180006e8a  jnz     short loc_180006EC1
0x180006e8c  mov     eax, dword ptr cs:_GUID_5cd52983_9449_11d2_963a_00c04f79adf0.Data4
0x180006e92  cmp     [r9+8], eax
0x180006e96  jnz     short loc_180006EC1
0x180006e98  mov     eax, dword ptr cs:_GUID_5cd52983_9449_11d2_963a_00c04f79adf0.Data4+4
0x180006e9e  cmp     [r9+0Ch], eax
0x180006ea2  jnz     short loc_180006EC1
0x180006ea4  mov     [r8], r10
0x180006ea7  xor     ebx, ebx
0x180006ea9  mov     rcx, [r8]
0x180006eac  mov     rdx, [rcx]
0x180006eaf  mov     rax, [rdx+8]
0x180006eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eb8  nop
0x180006eb9  mov     eax, ebx
0x180006ebb  add     rsp, 20h
0x180006ebf  pop     rbx
0x180006ec0  retn
0x180006ec1  mov     ebx, 80004002h
0x180006ec6  jmp     short loc_180006EB9
```
