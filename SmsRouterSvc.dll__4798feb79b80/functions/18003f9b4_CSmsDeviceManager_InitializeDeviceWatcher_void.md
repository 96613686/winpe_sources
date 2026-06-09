# CSmsDeviceManager::InitializeDeviceWatcher(void)

- ea: `0x18003f9b4`
- end: `0x18003fb11`
- name: `?InitializeDeviceWatcher@CSmsDeviceManager@@AEAAJXZ`
- size: `349`
- prototype: `__int64 __fastcall(CSmsDeviceManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003f550`

## callees

- `0x180003a60`
- `0x18003f9b4`
- `0x18006f010`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18003faf1`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18003faf1`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x18003faa4`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x18003faa4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSmsDeviceManager::InitializeDeviceWatcher(CSmsDeviceManager *this)
{
  int v2; // esi
  __int64 v3; // r8
  char v5; // [rsp+60h] [rbp-59h] BYREF
  __int64 v6; // [rsp+68h] [rbp-51h] BYREF
  __int64 v7; // [rsp+70h] [rbp-49h] BYREF
  DEVPROPKEY v8; // [rsp+78h] [rbp-41h]
  int v9; // [rsp+8Ch] [rbp-2Dh]
  __int64 v10; // [rsp+90h] [rbp-29h]
  int v11; // [rsp+98h] [rbp-21h]
  int v12; // [rsp+9Ch] [rbp-1Dh]
  __int64 *v13; // [rsp+A0h] [rbp-19h]
  __int64 v14; // [rsp+A8h] [rbp-11h]
  DEVPROPKEY v15; // [rsp+B0h] [rbp-9h]
  int v16; // [rsp+C4h] [rbp+Bh]
  __int64 v17; // [rsp+C8h] [rbp+Fh]
  int v18; // [rsp+D0h] [rbp+17h]
  int v19; // [rsp+D4h] [rbp+1Bh]
  char *v20; // [rsp+D8h] [rbp+1Fh]

  v6 = 0;
  v5 = -1;
  v7 = 2;
  v10 = 0;
  v14 = 2;
  v17 = 0;
  v8 = DEVPKEY_DeviceInterface_ClassGuid;
  v9 = 0;
  v11 = 13;
  v12 = 16;
  v13 = qword_180078690;
  v15 = DEVPKEY_DeviceInterface_Enabled;
  v16 = 0;
  v18 = 17;
  v19 = 1;
  v20 = &v5;
  v2 = DevCreateObjectQueryEx(1, 5, 0, 0, 2, &v7, 0, 0, CSmsDeviceManager::s_NetDeviceQueryCallback, this, &v6);
  if ( v2 >= 0 )
  {
    (**((void (__fastcall ***)(char *))this + 12))((char *)this + 96);
    v3 = *((_QWORD *)this + 31);
    *((_QWORD *)this + 31) = v6;
    v6 = v3;
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 12) + 8LL))((char *)this + 96);
  }
  if ( v6 )
    DevCloseObjectQuery(v6);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003f9b4  push    rbp
0x18003f9b6  push    rbx
0x18003f9b7  push    rsi
0x18003f9b8  push    rdi
0x18003f9b9  lea     rbp, [rsp-3Fh]
0x18003f9be  sub     rsp, 0F8h
0x18003f9c5  mov     rax, cs:__security_cookie
0x18003f9cc  xor     rax, rsp
0x18003f9cf  mov     [rbp+57h+var_30], rax
0x18003f9d3  mov     rdi, rcx
0x18003f9d6  mov     [rbp+57h+var_A8], 0
0x18003f9de  mov     [rbp+57h+var_B0], 0FFh
0x18003f9e2  mov     [rbp+57h+var_A0], 2
0x18003f9ea  xor     eax, eax
0x18003f9ec  mov     [rbp+57h+var_80], rax
0x18003f9f0  mov     [rbp+57h+var_68], 2
0x18003f9f8  mov     [rbp+57h+var_48], rax
0x18003f9fc  lea     edx, [rax+2]
0x18003f9ff  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x18003fa06  movups  [rbp+57h+var_98], xmm0
0x18003fa0a  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x18003fa10  mov     [rbp+57h+var_88], eax
0x18003fa13  mov     [rbp+57h+var_84], 0
0x18003fa1a  mov     [rbp+57h+var_78], 0Dh
0x18003fa21  mov     [rbp+57h+var_74], 10h
0x18003fa28  lea     rax, qword_180078690
0x18003fa2f  mov     [rbp+57h+var_70], rax
0x18003fa33  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x18003fa3a  movaps  [rbp+57h+var_60], xmm0
0x18003fa3e  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x18003fa44  mov     [rbp+57h+var_50], eax
0x18003fa47  mov     [rbp+57h+var_4C], 0
0x18003fa4e  mov     [rbp+57h+var_40], 11h
0x18003fa55  lea     ecx, [rdx-1]
0x18003fa58  mov     [rbp+57h+var_3C], ecx
0x18003fa5b  lea     rax, [rbp+57h+var_B0]
0x18003fa5f  mov     [rbp+57h+var_38], rax
0x18003fa63  lea     rax, [rbp+57h+var_A8]
0x18003fa67  mov     [rsp+110h+var_C0], rax
0x18003fa6c  mov     [rsp+110h+var_C8], rdi
0x18003fa71  lea     rax, ?s_NetDeviceQueryCallback@CSmsDeviceManager@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; CSmsDeviceManager::s_NetDeviceQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x18003fa78  mov     [rsp+110h+var_D0], rax
0x18003fa7d  mov     [rsp+110h+var_D8], 0
0x18003fa86  mov     [rsp+110h+var_E0], 0
0x18003fa8e  lea     rax, [rbp+57h+var_A0]
0x18003fa92  mov     [rsp+110h+var_E8], rax
0x18003fa97  mov     [rsp+110h+var_F0], edx
0x18003fa9b  xor     r9d, r9d
0x18003fa9e  xor     r8d, r8d
0x18003faa1  lea     edx, [rcx+4]
0x18003faa4  call    cs:__imp_DevCreateObjectQueryEx
0x18003faaa  mov     esi, eax
0x18003faac  test    eax, eax
0x18003faae  js      short loc_18003FAE8
0x18003fab0  lea     rbx, [rdi+60h]
0x18003fab4  mov     rcx, [rbx]
0x18003fab7  mov     rax, [rcx]
0x18003faba  mov     rcx, rbx
0x18003fabd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fac2  mov     r8, [rdi+0F8h]
0x18003fac9  mov     rdx, [rbp+57h+var_A8]
0x18003facd  mov     [rdi+0F8h], rdx
0x18003fad4  mov     [rbp+57h+var_A8], r8
0x18003fad8  mov     rax, [rbx]
0x18003fadb  mov     rcx, rbx
0x18003fade  mov     rax, [rax+8]
0x18003fae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fae7  nop
0x18003fae8  mov     rcx, [rbp+57h+var_A8]
0x18003faec  test    rcx, rcx
0x18003faef  jz      short loc_18003FAF7
0x18003faf1  call    cs:__imp_DevCloseObjectQuery
0x18003faf7  mov     eax, esi
0x18003faf9  mov     rcx, [rbp+57h+var_30]
0x18003fafd  xor     rcx, rsp; StackCookie
0x18003fb00  call    __security_check_cookie
0x18003fb05  add     rsp, 0F8h
0x18003fb0c  pop     rdi
0x18003fb0d  pop     rsi
0x18003fb0e  pop     rbx
0x18003fb0f  pop     rbp
0x18003fb10  retn
```
