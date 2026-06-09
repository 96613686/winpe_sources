# DeviceHelperDeviceInterfaceInSystemContainerAndRestricted

- ea: `0x180012e9c`
- end: `0x180013161`
- name: `DeviceHelperDeviceInterfaceInSystemContainerAndRestricted`
- size: `709`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a1e0`
- `0x180011c10`
- `0x180011cc0`

## callees

- `0x180003dc0`
- `0x180004c70`
- `0x180012460`
- `0x180012e9c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013131`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013131`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18001310b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180013121`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18001310b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180013121`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180012f83`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180013047`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180012f83`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180013047`

## pseudocode

```c
__int64 __fastcall DeviceHelperDeviceInterfaceInSystemContainerAndRestricted(unsigned __int16 *a1)
{
  int ObjectProperties; // edi
  LPVOID pv[2]; // [rsp+58h] [rbp-61h] BYREF
  __int128 v4; // [rsp+68h] [rbp-51h]
  DEVPROPKEY v5; // [rsp+78h] [rbp-41h]
  int v6; // [rsp+8Ch] [rbp-2Dh]
  __int64 v7; // [rsp+90h] [rbp-29h]
  DEVPROPKEY v8; // [rsp+A0h] [rbp-19h]
  int v9; // [rsp+B4h] [rbp-5h]
  __int64 v10; // [rsp+B8h] [rbp-1h]
  DEVPROPKEY v11; // [rsp+C0h] [rbp+7h]
  int v12; // [rsp+D4h] [rbp+1Bh]
  __int64 v13; // [rsp+D8h] [rbp+1Fh]

  v8 = DEVPKEY_Device_InstanceId;
  v11 = DEVPKEY_DeviceInterface_Restricted;
  v9 = 0;
  v10 = 0;
  v5 = DEVPKEY_Device_InLocalMachineContainer;
  v12 = 0;
  v13 = 0;
  v4 = 0;
  v6 = 0;
  v7 = 0;
  pv[1] = 0;
  pv[0] = 0;
  ObjectProperties = _DeviceHelperValidateInterfacePath(a1, (unsigned __int16 **)pv);
  if ( ObjectProperties >= 0 )
  {
    ObjectProperties = DevGetObjectProperties(1, pv[0], 0);
    if ( ObjectProperties >= 0 )
      ObjectProperties = -2147023728;
  }
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return (unsigned int)ObjectProperties;
}

```

## disassembly

```asm
0x180012e9c  mov     [rsp-8+arg_10], rbx
0x180012ea1  mov     [rsp-8+arg_18], rsi
0x180012ea6  push    rbp
0x180012ea7  push    rdi
0x180012ea8  push    r12
0x180012eaa  push    r13
0x180012eac  push    r14
0x180012eae  lea     rbp, [rsp-37h]
0x180012eb3  sub     rsp, 0F0h
0x180012eba  mov     rax, cs:__security_cookie
0x180012ec1  xor     rax, rsp
0x180012ec4  mov     [rbp+57h+var_30], rax
0x180012ec8  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x180012ecf  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x180012ed5  xor     r13d, r13d
0x180012ed8  mov     [rbp+57h+var_60], eax
0x180012edb  mov     r12, rdx
0x180012ede  mov     eax, cs:DEVPKEY_DeviceInterface_Restricted.pid
0x180012ee4  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x180012ee8  movaps  [rbp+57h+var_70], xmm0
0x180012eec  mov     ebx, r13d
0x180012eef  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Restricted.fmtid.Data1
0x180012ef6  mov     [rbp+57h+var_40], eax
0x180012ef9  mov     eax, cs:DEVPKEY_Device_InLocalMachineContainer.pid
0x180012eff  movaps  [rbp+57h+var_50], xmm0
0x180012f03  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InLocalMachineContainer.fmtid.Data1
0x180012f0a  mov     [rbp+57h+var_5C], r13d
0x180012f0e  mov     [rbp+57h+var_58], r13
0x180012f12  movups  [rbp+57h+var_98], xmm0
0x180012f16  mov     [rbp+57h+var_3C], r13d
0x180012f1a  xorps   xmm0, xmm0
0x180012f1d  mov     [rbp+57h+var_38], r13
0x180012f21  movups  [rbp+57h+var_A8], xmm0
0x180012f25  mov     [rbp+57h+var_88], eax
0x180012f28  mov     [rbp+57h+var_84], r13d
0x180012f2c  mov     [rbp+57h+var_80], r13
0x180012f30  mov     [rbp+57h+var_D0], r13d
0x180012f34  mov     [rbp+57h+var_C8], r13
0x180012f38  mov     [rbp+57h+var_CC], r13d
0x180012f3c  mov     [rbp+57h+var_C0], r13
0x180012f40  mov     [rbp+57h+var_B0], rbx
0x180012f44  mov     [rbp+57h+pv], r13
0x180012f48  call    ?_DeviceHelperValidateInterfacePath@@YAJPEBGPEAPEAG@Z; _DeviceHelperValidateInterfacePath(ushort const *,ushort * *)
0x180012f4d  mov     edi, eax
0x180012f4f  test    eax, eax
0x180012f51  js      loc_1800130F7
0x180012f57  mov     rdx, [rbp+57h+pv]
0x180012f5b  lea     rax, [rbp+57h+var_C8]
0x180012f5f  mov     [rsp+110h+var_E0], rax
0x180012f64  lea     esi, [r13+1]
0x180012f68  lea     rax, [rbp+57h+var_D0]
0x180012f6c  xor     r8d, r8d
0x180012f6f  mov     [rsp+110h+var_E8], rax
0x180012f74  lea     r9d, [r13+2]
0x180012f78  lea     rax, [rbp+57h+var_70]
0x180012f7c  mov     ecx, esi
0x180012f7e  mov     [rsp+110h+var_F0], rax
0x180012f83  call    cs:__imp_DevGetObjectProperties
0x180012f89  mov     edi, eax
0x180012f8b  test    eax, eax
0x180012f8d  js      loc_1800130F7
0x180012f93  mov     r8d, [rbp+57h+var_D0]
0x180012f97  test    r8d, r8d
0x180012f9a  jz      loc_1800130EC
0x180012fa0  cmp     [rbp+57h+var_C8], r13
0x180012fa4  jz      loc_1800130EC
0x180012faa  mov     r14b, sil
0x180012fad  mov     r10d, r13d
0x180012fb0  test    r8d, r8d
0x180012fb3  jz      short loc_180012FF9
0x180012fb5  mov     r9d, r13d
0x180012fb8  cmp     r9d, 2
0x180012fbc  jnb     short loc_180012FF1
0x180012fbe  mov     eax, r10d
0x180012fc1  lea     rdx, [rbp+57h+var_70]
0x180012fc5  mov     r11d, r9d
0x180012fc8  lea     rcx, [rax+rax*2]
0x180012fcc  mov     eax, r9d
0x180012fcf  shl     rax, 5
0x180012fd3  shl     rcx, 4
0x180012fd7  add     rdx, rax
0x180012fda  add     rcx, [rbp+57h+var_C8]
0x180012fde  call    ??8@YA_NAEBU_DEVPROPKEY@@0@Z; operator==(_DEVPROPKEY const &,_DEVPROPKEY const &)
0x180012fe3  test    al, al
0x180012fe5  jnz     short loc_180012FEC
0x180012fe7  add     r9d, esi
0x180012fea  jmp     short loc_180012FB8
0x180012fec  mov     qword ptr [rbp+r11*8+57h+var_A8], rcx
0x180012ff1  add     r10d, esi
0x180012ff4  cmp     r10d, r8d
0x180012ff7  jb      short loc_180012FB5
0x180012ff9  mov     rax, qword ptr [rbp+57h+var_A8+8]
0x180012ffd  test    rax, rax
0x180013000  jz      short loc_18001301A
0x180013002  cmp     dword ptr [rax+20h], 11h
0x180013006  jnz     short loc_18001301A
0x180013008  mov     rax, [rax+28h]
0x18001300c  test    rax, rax
0x18001300f  jz      short loc_18001301A
0x180013011  mov     al, [rax]
0x180013013  neg     al
0x180013015  sbb     cl, cl
0x180013017  and     r14b, cl
0x18001301a  mov     rdx, qword ptr [rbp+57h+var_A8]
0x18001301e  lea     rax, [rbp+57h+var_C0]
0x180013022  mov     [rsp+110h+var_E0], rax
0x180013027  xor     r8d, r8d
0x18001302a  lea     rax, [rbp+57h+var_CC]
0x18001302e  mov     r9d, esi
0x180013031  mov     [rsp+110h+var_E8], rax
0x180013036  lea     rax, [rbp+57h+var_98]
0x18001303a  mov     rdx, [rdx+28h]
0x18001303e  lea     ecx, [r8+3]
0x180013042  mov     [rsp+110h+var_F0], rax
0x180013047  call    cs:__imp_DevGetObjectProperties
0x18001304d  mov     edi, eax
0x18001304f  test    eax, eax
0x180013051  js      loc_1800130F7
0x180013057  mov     r9d, [rbp+57h+var_CC]
0x18001305b  test    r9d, r9d
0x18001305e  jz      loc_1800130E5
0x180013064  cmp     [rbp+57h+var_C0], r13
0x180013068  jz      short loc_1800130E5
0x18001306a  mov     r10d, r13d
0x18001306d  test    r9d, r9d
0x180013070  jz      short loc_1800130B9
0x180013072  mov     r8d, r13d
0x180013075  cmp     r8d, esi
0x180013078  jnb     short loc_1800130AD
0x18001307a  mov     eax, r10d
0x18001307d  lea     rdx, [rbp+57h+var_98]
0x180013081  mov     r11d, r8d
0x180013084  lea     rcx, [rax+rax*2]
0x180013088  mov     eax, r8d
0x18001308b  shl     rax, 5
0x18001308f  shl     rcx, 4
0x180013093  add     rdx, rax
0x180013096  add     rcx, [rbp+57h+var_C0]
0x18001309a  call    ??8@YA_NAEBU_DEVPROPKEY@@0@Z; operator==(_DEVPROPKEY const &,_DEVPROPKEY const &)
0x18001309f  test    al, al
0x1800130a1  jnz     short loc_1800130A8
0x1800130a3  add     r8d, esi
0x1800130a6  jmp     short loc_180013075
0x1800130a8  mov     [rbp+r11*8+57h+var_B0], rcx
0x1800130ad  add     r10d, esi
0x1800130b0  cmp     r10d, r9d
0x1800130b3  jb      short loc_180013072
0x1800130b5  mov     rbx, [rbp+57h+var_B0]
0x1800130b9  test    rbx, rbx
0x1800130bc  jz      short loc_1800130E5
0x1800130be  cmp     dword ptr [rbx+20h], 11h
0x1800130c2  jnz     short loc_1800130E5
0x1800130c4  mov     rax, [rbx+28h]
0x1800130c8  test    rax, rax
0x1800130cb  jz      short loc_1800130E5
0x1800130cd  cmp     [rax], r13b
0x1800130d0  setnz   al
0x1800130d3  test    r14b, r14b
0x1800130d6  jz      short loc_1800130DC
0x1800130d8  test    al, al
0x1800130da  jnz     short loc_1800130DF
0x1800130dc  mov     sil, r13b
0x1800130df  mov     [r12], sil
0x1800130e3  jmp     short loc_1800130FB
0x1800130e5  mov     edi, 80070490h
0x1800130ea  jmp     short loc_1800130FB
0x1800130ec  mov     r9d, [rbp+57h+var_CC]
0x1800130f0  mov     edi, 80070490h
0x1800130f5  jmp     short loc_1800130FF
0x1800130f7  mov     r9d, [rbp+57h+var_CC]
0x1800130fb  mov     r8d, [rbp+57h+var_D0]
0x1800130ff  test    r8d, r8d
0x180013102  jz      short loc_180013115
0x180013104  mov     rdx, [rbp+57h+var_C8]
0x180013108  mov     ecx, r8d
0x18001310b  call    cs:__imp_DevFreeObjectProperties
0x180013111  mov     r9d, [rbp+57h+var_CC]
0x180013115  test    r9d, r9d
0x180013118  jz      short loc_180013127
0x18001311a  mov     rdx, [rbp+57h+var_C0]
0x18001311e  mov     ecx, r9d
0x180013121  call    cs:__imp_DevFreeObjectProperties
0x180013127  cmp     [rbp+57h+pv], r13
0x18001312b  jz      short loc_180013137
0x18001312d  mov     rcx, [rbp+57h+pv]; pv
0x180013131  call    cs:__imp_CoTaskMemFree
0x180013137  mov     eax, edi
0x180013139  mov     rcx, [rbp+57h+var_30]
0x18001313d  xor     rcx, rsp; StackCookie
0x180013140  call    __security_check_cookie
0x180013145  lea     r11, [rsp+110h+var_20]
0x18001314d  mov     rbx, [r11+40h]
0x180013151  mov     rsi, [r11+48h]
0x180013155  mov     rsp, r11
0x180013158  pop     r14
0x18001315a  pop     r13
0x18001315c  pop     r12
0x18001315e  pop     rdi
0x18001315f  pop     rbp
0x180013160  retn
```
