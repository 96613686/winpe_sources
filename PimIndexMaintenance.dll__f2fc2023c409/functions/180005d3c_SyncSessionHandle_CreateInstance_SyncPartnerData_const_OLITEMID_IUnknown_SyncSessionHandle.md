# SyncSessionHandle::CreateInstance(SyncPartnerData const &,OLITEMID,IUnknown *,SyncSessionHandle * *)

- ea: `0x180005d3c`
- end: `0x180005e13`
- name: `?CreateInstance@SyncSessionHandle@@SAJAEBUSyncPartnerData@@UOLITEMID@@PEAUIUnknown@@PEAPEAV1@@Z`
- size: `215`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, SyncSessionHandle **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000523c`

## callees

- `0x1800012fc`
- `0x180002da8`
- `0x180003d88`
- `0x180005d3c`
- `0x1800085a0`

## string_xrefs

- `0x180005dc5`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180005df0`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall SyncSessionHandle::CreateInstance(__int64 a1, __int64 *a2, __int64 a3, SyncSessionHandle **a4)
{
  SyncSessionHandle *v8; // rax
  SyncSessionHandle *v9; // rbx
  __int64 v10; // xmm0_8
  int v11; // eax
  unsigned int v12; // edi
  __int64 v14; // [rsp+30h] [rbp-38h] BYREF
  int v15; // [rsp+38h] [rbp-30h]

  v8 = (SyncSessionHandle *)operator new(0x28u);
  v9 = v8;
  if ( v8 )
  {
    v10 = *a2;
    *(_QWORD *)v8 = 0;
    *((_QWORD *)v8 + 1) = 0;
    *((_QWORD *)v8 + 2) = 0;
    *((_DWORD *)v8 + 6) = 1;
    *((_DWORD *)v8 + 7) = -1;
    *((_DWORD *)v8 + 8) = 0;
    v15 = *((_DWORD *)a2 + 2);
    v14 = v10;
    v11 = SyncSessionHandle::Initialize(v8, a1, &v14, a3);
    v12 = v11;
    if ( v11 >= 0 )
    {
      *a4 = v9;
      return 0;
    }
    else
    {
      Log_HREvent(
        (unsigned int)v11,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        152);
      tlx::_delete<SyncSessionHandle>(v9);
      return v12;
    }
  }
  else
  {
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      148);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180005d3c  push    rbx
0x180005d3e  push    rbp
0x180005d3f  push    rsi
0x180005d40  push    rdi
0x180005d41  push    r14
0x180005d43  sub     rsp, 40h
0x180005d47  mov     r14, rcx
0x180005d4a  mov     rsi, r9
0x180005d4d  mov     ecx, 28h ; '('; Size
0x180005d52  mov     rbp, r8
0x180005d55  mov     rdi, rdx
0x180005d58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005d5d  mov     rbx, rax
0x180005d60  test    rax, rax
0x180005d63  jz      loc_180005DEB
0x180005d69  movsd   xmm0, qword ptr [rdi]
0x180005d6d  lea     r8, [rsp+68h+var_38]
0x180005d72  mov     qword ptr [rax], 0
0x180005d79  mov     r9, rbp
0x180005d7c  mov     qword ptr [rax+8], 0
0x180005d84  mov     rdx, r14
0x180005d87  mov     qword ptr [rax+10h], 0
0x180005d8f  mov     rcx, rbx
0x180005d92  mov     dword ptr [rax+18h], 1
0x180005d99  mov     dword ptr [rax+1Ch], 0FFFFFFFFh
0x180005da0  mov     dword ptr [rax+20h], 0
0x180005da7  mov     eax, [rdi+8]
0x180005daa  mov     [rsp+68h+var_30], eax
0x180005dae  movsd   [rsp+68h+var_38], xmm0
0x180005db4  call    ?Initialize@SyncSessionHandle@@AEAAJAEBUSyncPartnerData@@UOLITEMID@@PEAUIUnknown@@@Z; SyncSessionHandle::Initialize(SyncPartnerData const &,OLITEMID,IUnknown *)
0x180005db9  mov     edi, eax
0x180005dbb  test    eax, eax
0x180005dbd  jns     short loc_180005DE4
0x180005dbf  mov     r9d, 98h
0x180005dc5  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180005dcc  mov     edx, 1
0x180005dd1  mov     ecx, eax
0x180005dd3  call    Log_HREvent
0x180005dd8  mov     rcx, rbx; Block
0x180005ddb  call    ??$_delete@VSyncSessionHandle@@@tlx@@YAXPEAVSyncSessionHandle@@@Z; tlx::_delete<SyncSessionHandle>(SyncSessionHandle *)
0x180005de0  mov     eax, edi
0x180005de2  jmp     short loc_180005E08
0x180005de4  mov     [rsi], rbx
0x180005de7  xor     eax, eax
0x180005de9  jmp     short loc_180005E08
0x180005deb  mov     ebx, 8007000Eh
0x180005df0  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180005df7  mov     ecx, ebx
0x180005df9  mov     r9d, 94h
0x180005dff  xor     edx, edx
0x180005e01  call    Log_HREvent
0x180005e06  mov     eax, ebx
0x180005e08  add     rsp, 40h
0x180005e0c  pop     r14
0x180005e0e  pop     rdi
0x180005e0f  pop     rsi
0x180005e10  pop     rbp
0x180005e11  pop     rbx
0x180005e12  retn
```
