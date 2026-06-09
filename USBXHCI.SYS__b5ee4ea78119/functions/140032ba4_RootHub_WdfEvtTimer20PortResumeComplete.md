# RootHub_WdfEvtTimer20PortResumeComplete

- ea: `0x140032ba4`
- end: `0x140032e9b`
- name: `RootHub_WdfEvtTimer20PortResumeComplete`
- size: `759`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140032b60`

## callees

- `0x14001a214`
- `0x14001ac48`
- `0x14001ad0c`
- `0x14001bb78`
- `0x14001d02c`
- `0x14001d118`
- `0x14001f830`
- `0x14001fb30`
- `0x140021830`
- `0x140021964`
- `0x140032ba4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140032db3`
- `ntoskrnl!KeGetCurrentIrql` at `0x140032db3`

## string_xrefs

- `0x140032dd6`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall RootHub_WdfEvtTimer20PortResumeComplete(_QWORD *a1, int a2)
{
  __int64 v4; // rcx
  __int64 v5; // r15
  __int64 result; // rax
  int v7; // edx
  unsigned int v8; // r13d
  int v9; // edx
  __int64 v10; // r12
  int *v11; // r12
  int Ulong; // eax
  int v13; // edx
  int v14; // ebx
  int v15; // ebx
  __int64 v16; // rax
  char v17; // al
  int v18; // edx
  __int64 v19; // r12
  int v20; // eax
  int v21; // edx
  int v22; // ebx
  unsigned int v23; // ebx
  signed __int32 v24[8]; // [rsp+0h] [rbp-68h] BYREF
  int v25; // [rsp+70h] [rbp+8h] BYREF
  __int64 v26; // [rsp+80h] [rbp+18h]

  if ( *(_BYTE *)(a1[1] + 1041LL) && KeGetCurrentIrql() )
    Debug_FreAssertMsg(
      "Code Path Requires Passive Level",
      0,
      "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\roothub.c",
      4719);
  v4 = a1[1];
  v5 = *(_QWORD *)(v4 + 88);
  result = Controller_IsControllerAccessible(v4);
  if ( (_BYTE)result )
  {
    v8 = a2 - 1;
    RootHub_AcquireReadModifyWriteLock(a1, (unsigned int)(a2 - 1));
    v10 = a1[5];
    v26 = 16LL * (unsigned int)(a2 - 1);
    v11 = (int *)(v26 + v10);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1[1] + 72LL),
        v9,
        11,
        221,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        a2);
    }
    Ulong = XilRegister_ReadUlong(v5, v11);
    v14 = Ulong;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 4;
      WPP_RECORDER_SF_D(
        *(_QWORD *)(a1[1] + 72LL),
        v13,
        11,
        222,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        Ulong);
    }
    v15 = v14 & 0xE00C200 | 0x410000;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 4;
      WPP_RECORDER_SF_D(
        *(_QWORD *)(a1[1] + 72LL),
        v13,
        11,
        223,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        v15);
    }
    v16 = *(_QWORD *)(v5 + 8);
    v25 = v15;
    if ( *(_BYTE *)(v16 + 1041) )
    {
      Register_WriteSecureMmio(v5, v11, 2, &v25);
    }
    else
    {
      *v11 = v15;
      _InterlockedOr(v24, 0);
    }
    RootHub_ReleaseReadModifyWriteLock(a1, v8);
    v17 = XilRegister_ReadUlong(v5, v11);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = 4;
      WPP_RECORDER_SF_D(
        *(_QWORD *)(a1[1] + 72LL),
        v18,
        11,
        224,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
        v17);
    }
    result = a1[1];
    if ( (*(_DWORD *)(result + 736) & 0x8000000) != 0 )
    {
      result = a1[6];
      if ( *(_BYTE *)(120LL * v8 + result + 23) )
      {
        v19 = v26 + a1[5];
        RootHub_AcquireReadModifyWriteLock(a1, v8);
        v20 = XilRegister_ReadUlong(v5, v19 + 4);
        v22 = v20;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v21) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(a1[1] + 72LL),
            v21,
            11,
            225,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v20);
        }
        v23 = v22 | 0x10000;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v21) = 4;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(a1[1] + 72LL),
            v21,
            11,
            226,
            (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
            v23);
        }
        XilRegister_WriteUlong(v5, v19 + 4, v23);
        return RootHub_ReleaseReadModifyWriteLock(a1, v8);
      }
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 4;
    return WPP_RECORDER_SF_(
             *(_QWORD *)(a1[1] + 72LL),
             v7,
             11,
             220,
             (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140032ba4  mov     [rsp+arg_8], rbx
0x140032ba9  push    rbp
0x140032baa  push    rsi
0x140032bab  push    rdi
0x140032bac  push    r12
0x140032bae  push    r13
0x140032bb0  push    r14
0x140032bb2  push    r15
0x140032bb4  sub     rsp, 30h
0x140032bb8  mov     rax, [rcx+8]
0x140032bbc  mov     ebx, edx
0x140032bbe  mov     rdi, rcx
0x140032bc1  cmp     byte ptr [rax+411h], 0
0x140032bc8  jnz     loc_140032DB3
0x140032bce  mov     rcx, [rdi+8]
0x140032bd2  mov     r15, [rcx+58h]
0x140032bd6  call    Controller_IsControllerAccessible
0x140032bdb  test    al, al
0x140032bdd  jz      loc_140032CC7
0x140032be3  lea     r13d, [rbx-1]
0x140032be7  mov     rcx, rdi
0x140032bea  mov     edx, r13d
0x140032bed  call    RootHub_AcquireReadModifyWriteLock
0x140032bf2  mov     r12, [rdi+28h]
0x140032bf6  mov     ecx, r13d
0x140032bf9  shl     rcx, 4
0x140032bfd  mov     [rsp+68h+arg_10], rcx
0x140032c05  add     r12, rcx
0x140032c08  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140032c0f  mov     ebp, 0Bh
0x140032c14  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140032c1b  lea     r14, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x140032c22  jnz     loc_140032D00
0x140032c28  mov     rdx, r12
0x140032c2b  mov     rcx, r15
0x140032c2e  call    XilRegister_ReadUlong
0x140032c33  mov     ebx, eax
0x140032c35  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140032c3c  jnz     loc_140032D4C
0x140032c42  and     ebx, 0E00C200h
0x140032c48  or      ebx, 410000h
0x140032c4e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140032c55  jnz     loc_140032D26
0x140032c5b  mov     rax, [r15+8]
0x140032c5f  mov     [rsp+68h+arg_0], ebx
0x140032c63  cmp     byte ptr [rax+411h], 0
0x140032c6a  jnz     loc_140032D72
0x140032c70  mov     [r12], ebx
0x140032c74  lock or [rsp+68h+var_68], 0
0x140032c79  mov     edx, r13d
0x140032c7c  mov     rcx, rdi
0x140032c7f  call    RootHub_ReleaseReadModifyWriteLock
0x140032c84  mov     rdx, r12
0x140032c87  mov     rcx, r15
0x140032c8a  call    XilRegister_ReadUlong
0x140032c8f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140032c96  jnz     loc_140032D8D
0x140032c9c  mov     rax, [rdi+8]
0x140032ca0  mov     ecx, [rax+2E0h]
0x140032ca6  bt      rcx, 1Bh
0x140032cab  jb      loc_140032DE7
0x140032cb1  mov     rbx, [rsp+68h+arg_8]
0x140032cb6  add     rsp, 30h
0x140032cba  pop     r15
0x140032cbc  pop     r14
0x140032cbe  pop     r13
0x140032cc0  pop     r12
0x140032cc2  pop     rdi
0x140032cc3  pop     rsi
0x140032cc4  pop     rbp
0x140032cc5  retn
0x140032cc7  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140032cce  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140032cd5  jz      short loc_140032CB1
0x140032cd7  mov     rcx, [rdi+8]
0x140032cdb  lea     r14, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x140032ce2  mov     r9d, 0DCh
0x140032ce8  mov     [rsp+68h+var_48], r14
0x140032ced  mov     r8d, 0Bh
0x140032cf3  mov     dl, 4
0x140032cf5  mov     rcx, [rcx+48h]
0x140032cf9  call    WPP_RECORDER_SF_
0x140032cfe  jmp     short loc_140032CB1
0x140032d00  mov     rcx, [rdi+8]
0x140032d04  mov     r9d, 0DDh
0x140032d0a  mov     [rsp+68h+var_40], ebx
0x140032d0e  mov     r8d, ebp
0x140032d11  mov     dl, 4
0x140032d13  mov     [rsp+68h+var_48], r14
0x140032d18  mov     rcx, [rcx+48h]
0x140032d1c  call    WPP_RECORDER_SF_d
0x140032d21  jmp     loc_140032C28
0x140032d26  mov     rcx, [rdi+8]
0x140032d2a  mov     r9d, 0DFh
0x140032d30  mov     [rsp+68h+var_40], ebx
0x140032d34  mov     r8d, ebp
0x140032d37  mov     dl, 4
0x140032d39  mov     [rsp+68h+var_48], r14
0x140032d3e  mov     rcx, [rcx+48h]
0x140032d42  call    WPP_RECORDER_SF_D
0x140032d47  jmp     loc_140032C5B
0x140032d4c  mov     rcx, [rdi+8]
0x140032d50  mov     r9d, 0DEh
0x140032d56  mov     [rsp+68h+var_40], ebx
0x140032d5a  mov     r8d, ebp
0x140032d5d  mov     dl, 4
0x140032d5f  mov     [rsp+68h+var_48], r14
0x140032d64  mov     rcx, [rcx+48h]
0x140032d68  call    WPP_RECORDER_SF_D
0x140032d6d  jmp     loc_140032C42
0x140032d72  lea     r9, [rsp+68h+arg_0]
0x140032d77  mov     r8d, 2
0x140032d7d  mov     rdx, r12
0x140032d80  mov     rcx, r15
0x140032d83  call    Register_WriteSecureMmio
0x140032d88  jmp     loc_140032C79
0x140032d8d  mov     rcx, [rdi+8]
0x140032d91  mov     r9d, 0E0h
0x140032d97  mov     [rsp+68h+var_40], eax
0x140032d9b  mov     r8d, ebp
0x140032d9e  mov     dl, 4
0x140032da0  mov     [rsp+68h+var_48], r14
0x140032da5  mov     rcx, [rcx+48h]
0x140032da9  call    WPP_RECORDER_SF_D
0x140032dae  jmp     loc_140032C9C
0x140032db3  call    cs:__imp_KeGetCurrentIrql
0x140032dba  nop     dword ptr [rax+rax+00h]
0x140032dbf  test    al, al
0x140032dc1  jz      loc_140032BCE
0x140032dc7  mov     r9d, 126Fh
0x140032dcd  lea     r8, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140032dd4  xor     edx, edx
0x140032dd6  lea     rcx, aCodePathRequir; "Code Path Requires Passive Level"
0x140032ddd  call    Debug_FreAssertMsg
0x140032de2  jmp     loc_140032BCE
0x140032de7  mov     eax, r13d
0x140032dea  imul    rcx, rax, 78h ; 'x'
0x140032dee  mov     rax, [rdi+30h]
0x140032df2  cmp     byte ptr [rcx+rax+17h], 0
0x140032df7  jz      loc_140032CB1
0x140032dfd  mov     r12, [rdi+28h]
0x140032e01  mov     edx, r13d
0x140032e04  add     r12, [rsp+68h+arg_10]
0x140032e0c  mov     rcx, rdi
0x140032e0f  call    RootHub_AcquireReadModifyWriteLock
0x140032e14  lea     rdx, [r12+4]
0x140032e19  mov     rcx, r15
0x140032e1c  call    XilRegister_ReadUlong
0x140032e21  mov     ebx, eax
0x140032e23  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140032e2a  jz      short loc_140032E4D
0x140032e2c  mov     rcx, [rdi+8]
0x140032e30  mov     r9d, 0E1h
0x140032e36  mov     [rsp+68h+var_40], eax
0x140032e3a  mov     r8d, ebp
0x140032e3d  mov     dl, 4
0x140032e3f  mov     [rsp+68h+var_48], r14
0x140032e44  mov     rcx, [rcx+48h]
0x140032e48  call    WPP_RECORDER_SF_D
0x140032e4d  bts     ebx, 10h
0x140032e51  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140032e58  jz      short loc_140032E7B
0x140032e5a  mov     rcx, [rdi+8]
0x140032e5e  mov     r9d, 0E2h
0x140032e64  mov     [rsp+68h+var_40], ebx
0x140032e68  mov     r8d, ebp
0x140032e6b  mov     dl, 4
0x140032e6d  mov     [rsp+68h+var_48], r14
0x140032e72  mov     rcx, [rcx+48h]
0x140032e76  call    WPP_RECORDER_SF_D
0x140032e7b  mov     r8d, ebx
0x140032e7e  lea     rdx, [r12+4]
0x140032e83  mov     rcx, r15
0x140032e86  call    XilRegister_WriteUlong
0x140032e8b  mov     edx, r13d
0x140032e8e  mov     rcx, rdi
0x140032e91  call    RootHub_ReleaseReadModifyWriteLock
0x140032e96  jmp     loc_140032CB1
```
