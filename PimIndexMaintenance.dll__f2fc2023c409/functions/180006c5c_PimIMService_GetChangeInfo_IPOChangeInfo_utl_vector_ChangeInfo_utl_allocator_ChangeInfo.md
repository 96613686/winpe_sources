# PimIMService::GetChangeInfo(IPOChangeInfo *,utl::vector<ChangeInfo,utl::allocator<ChangeInfo>> &)

- ea: `0x180006c5c`
- end: `0x180006e14`
- name: `?GetChangeInfo@PimIMService@@AEAAJPEAUIPOChangeInfo@@AEAV?$vector@UChangeInfo@@V?$allocator@UChangeInfo@@@utl@@@utl@@@Z`
- size: `440`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000523c`

## callees

- `0x180002da8`
- `0x1800039b0`
- `0x1800067c0`
- `0x180006c5c`
- `0x18000c5b8`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x180006cbe`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180006d26`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180006dfa`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::GetChangeInfo(__int64 a1, __int64 *a2, __int64 a3)
{
  int v5; // esi
  __int64 v6; // r9
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // edi
  __int128 v12; // xmm6
  void *v13; // rax
  _OWORD *v14; // rax
  unsigned int v15; // [rsp+48h] [rbp-19h] BYREF
  int v16; // [rsp+4Ch] [rbp-15h] BYREF
  __int64 v17; // [rsp+50h] [rbp-11h] BYREF
  unsigned int v18; // [rsp+58h] [rbp-9h]
  _OWORD v19[2]; // [rsp+60h] [rbp-1h] BYREF
  __int128 v20; // [rsp+80h] [rbp+1Fh] BYREF

  v16 = 12;
  v17 = 0;
  v18 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, int *, __int64 *))(*a2 + 32))(a2, 0, &v16, &v17);
  if ( v5 < 0 )
  {
    v6 = 2766;
LABEL_3:
    Log_HREvent(
      (unsigned int)v5,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v6);
    return (unsigned int)v5;
  }
  v8 = *a2;
  v15 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v8 + 24))(a2, &v15);
  if ( v5 < 0 )
  {
    v6 = 2770;
    goto LABEL_3;
  }
  v9 = *a2;
  v20 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v9 + 64))(a2, &v20);
  v11 = v10;
  if ( v10 < 0 )
  {
    Log_HREvent(
      (unsigned int)v10,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2775);
    return v11;
  }
  v12 = v20;
  *((_QWORD *)&v19[0] + 1) = __PAIR64__(v15, v18);
  v19[1] = v20;
  *(_QWORD *)&v19[0] = v17;
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
  {
    v13 = _t_address();
    EtwTraceMessage(&ETWMESSAGE, v13, &v15);
  }
  v14 = *(_OWORD **)(a3 + 8);
  if ( v14 != *(_OWORD **)(a3 + 16) )
  {
    *v14 = v19[0];
    v14[1] = v12;
    *(_QWORD *)(a3 + 8) += 32LL;
    return 0;
  }
  if ( (unsigned __int8)utl::vector<ChangeInfo,utl::allocator<ChangeInfo>>::_PushBackOne2<ChangeInfo const &>(a3, v19) )
    return 0;
  Log_HREvent(
    2147942414LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
    2787);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180006c5c  mov     rax, rsp
0x180006c5f  mov     [rax+8], rbx
0x180006c63  push    rbp
0x180006c64  push    rsi
0x180006c65  push    rdi
0x180006c66  lea     rbp, [rax-5Fh]
0x180006c6a  sub     rsp, 0A0h
0x180006c71  movaps  xmmword ptr [rax-28h], xmm6
0x180006c75  mov     rax, cs:__security_cookie
0x180006c7c  xor     rax, rsp
0x180006c7f  mov     [rbp+57h+var_28], rax
0x180006c83  xor     eax, eax
0x180006c85  mov     [rbp+57h+var_6C], 0Ch
0x180006c8c  mov     [rbp+57h+var_68], rax
0x180006c90  lea     r9, [rbp+57h+var_68]
0x180006c94  mov     [rbp+57h+var_60], eax
0x180006c97  mov     rdi, rdx
0x180006c9a  mov     rax, [rdx]
0x180006c9d  mov     rbx, r8
0x180006ca0  lea     r8, [rbp+57h+var_6C]
0x180006ca4  xor     edx, edx
0x180006ca6  mov     rcx, rdi
0x180006ca9  mov     rax, [rax+20h]
0x180006cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cb2  mov     esi, eax
0x180006cb4  test    eax, eax
0x180006cb6  jns     short loc_180006CD8
0x180006cb8  mov     r9d, 0ACEh
0x180006cbe  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180006cc5  mov     edx, 1
0x180006cca  mov     ecx, esi
0x180006ccc  call    Log_HREvent
0x180006cd1  mov     eax, esi
0x180006cd3  jmp     loc_180006DC1
0x180006cd8  mov     rax, [rdi]
0x180006cdb  lea     rdx, [rbp+57h+var_70]
0x180006cdf  mov     rcx, rdi
0x180006ce2  mov     [rbp+57h+var_70], 0
0x180006ce9  mov     rax, [rax+18h]
0x180006ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cf2  mov     esi, eax
0x180006cf4  test    eax, eax
0x180006cf6  jns     short loc_180006D00
0x180006cf8  mov     r9d, 0AD2h
0x180006cfe  jmp     short loc_180006CBE
0x180006d00  mov     rax, [rdi]
0x180006d03  lea     rdx, [rbp+57h+var_38]
0x180006d07  xorps   xmm0, xmm0
0x180006d0a  mov     rcx, rdi
0x180006d0d  movups  [rbp+57h+var_38], xmm0
0x180006d11  mov     rax, [rax+40h]
0x180006d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d1a  mov     edi, eax
0x180006d1c  test    eax, eax
0x180006d1e  jns     short loc_180006D40
0x180006d20  mov     r9d, 0AD7h
0x180006d26  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180006d2d  mov     edx, 1
0x180006d32  mov     ecx, eax
0x180006d34  call    Log_HREvent
0x180006d39  mov     eax, edi
0x180006d3b  jmp     loc_180006DC1
0x180006d40  mov     eax, [rbp+57h+var_60]
0x180006d43  mov     r9d, 4
0x180006d49  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, r9b
0x180006d50  movups  xmm6, [rbp+57h+var_38]
0x180006d54  mov     dword ptr [rbp+57h+var_58+8], eax
0x180006d57  movsd   xmm0, [rbp+57h+var_68]
0x180006d5c  mov     eax, [rbp+57h+var_70]
0x180006d5f  movups  [rbp+57h+var_48], xmm6
0x180006d63  mov     dword ptr [rbp+57h+var_58+0Ch], eax
0x180006d66  movsd   qword ptr [rbp+57h+var_58], xmm0
0x180006d6b  jz      short loc_180006DA5
0x180006d6d  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x180006d72  mov     [rsp+0B0h+var_78], 0FFFFFFFFFFFFFFFFh
0x180006d7b  lea     r8, [rbp+57h+var_70]
0x180006d7f  mov     rdx, rax; void *
0x180006d82  mov     [rsp+0B0h+var_80], 0
0x180006d8b  lea     rax, [rbp+57h+var_60]
0x180006d8f  mov     [rsp+0B0h+var_88], r9
0x180006d94  lea     rcx, _ETWMESSAGE; EventDescriptor
0x180006d9b  mov     [rsp+0B0h+var_90], rax
0x180006da0  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x180006da5  mov     rax, [rbx+8]
0x180006da9  cmp     rax, [rbx+10h]
0x180006dad  jz      short loc_180006DE5
0x180006daf  movups  xmm0, [rbp+57h+var_58]
0x180006db3  movups  xmmword ptr [rax], xmm0
0x180006db6  movups  xmmword ptr [rax+10h], xmm6
0x180006dba  add     qword ptr [rbx+8], 20h ; ' '
0x180006dbf  xor     eax, eax
0x180006dc1  mov     rcx, [rbp+57h+var_28]
0x180006dc5  xor     rcx, rsp; StackCookie
0x180006dc8  call    __security_check_cookie
0x180006dcd  lea     r11, [rsp+0B0h+var_10]
0x180006dd5  mov     rbx, [r11+20h]
0x180006dd9  movaps  xmm6, xmmword ptr [r11-10h]
0x180006dde  mov     rsp, r11
0x180006de1  pop     rdi
0x180006de2  pop     rsi
0x180006de3  pop     rbp
0x180006de4  retn
0x180006de5  lea     rdx, [rbp+57h+var_58]
0x180006de9  mov     rcx, rbx
0x180006dec  call    ??$_PushBackOne2@AEBUChangeInfo@@@?$vector@UChangeInfo@@V?$allocator@UChangeInfo@@@utl@@@utl@@AEAA_NAEBUChangeInfo@@@Z; utl::vector<ChangeInfo,utl::allocator<ChangeInfo>>::_PushBackOne2<ChangeInfo const &>(ChangeInfo const &)
0x180006df1  test    al, al
0x180006df3  jnz     short loc_180006DBF
0x180006df5  mov     ebx, 8007000Eh
0x180006dfa  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180006e01  mov     ecx, ebx
0x180006e03  mov     r9d, 0AE3h
0x180006e09  xor     edx, edx
0x180006e0b  call    Log_HREvent
0x180006e10  mov     eax, ebx
0x180006e12  jmp     short loc_180006DC1
```
