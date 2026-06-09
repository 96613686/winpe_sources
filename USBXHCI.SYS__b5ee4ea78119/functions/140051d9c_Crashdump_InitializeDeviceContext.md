# Crashdump_InitializeDeviceContext

- ea: `0x140051d9c`
- end: `0x140051fc5`
- name: `Crashdump_InitializeDeviceContext`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140052940`

## callees

- `0x14002499c`
- `0x14002e9b0`
- `0x140051d9c`
- `0x140054410`
- `0x1400556c8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140051e00`
- `ntoskrnl!RtlCompareMemory` at `0x140051e00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051f97`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051f97`
- `ntoskrnl!ExAllocatePool2` at `0x140051e83`
- `ntoskrnl!ExAllocatePool2` at `0x140051f26`
- `ntoskrnl!ExAllocatePool2` at `0x140051e83`
- `ntoskrnl!ExAllocatePool2` at `0x140051f26`

## pseudocode

```c
__int64 __fastcall Crashdump_InitializeDeviceContext(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int i; // edi
  __int64 v10; // rsi
  unsigned int v11; // eax
  __int64 DeviceContextBufferVA; // rax
  int v13; // r9d
  __int64 v14; // r14
  int v15; // ebx
  void *Pool2; // rdi
  __int64 j; // r14
  __int64 v18; // r13
  __int64 v19; // rax
  __int64 v20; // r12
  __int64 v21; // rax
  __int64 v23; // [rsp+40h] [rbp-48h]
  int v24; // [rsp+90h] [rbp+8h]

  for ( i = 1; ; ++i )
  {
    if ( i > *(_DWORD *)(a1 + 96) )
      return (unsigned int)-1073741275;
    v10 = *(_QWORD *)(XilDeviceSlot_GetUsbDeviceHandleArray(a1) + 8LL * i);
    if ( v10 )
    {
      v11 = *(_DWORD *)(v10 + 36);
      if ( v11 == *(_DWORD *)(a4 + 4)
        && RtlCompareMemory((const void *)(v10 + 44), (const void *)(a4 + 12), 4LL * v11) == 4LL * v11 )
      {
        break;
      }
    }
  }
  DeviceContextBufferVA = XilCoreUsbDevice_GetDeviceContextBufferVA(v10 + (*(_BYTE *)(v10 + 665) != 0 ? 624LL : 616LL));
  LOBYTE(v13) = *(_BYTE *)(v10 + 143);
  v14 = DeviceContextBufferVA;
  v23 = DeviceContextBufferVA;
  v15 = Crashdump_UsbDevice_Initialize(a5, a2, a3, v13, DeviceContextBufferVA, v10, *(_DWORD *)(a4 + 4));
  if ( v15 >= 0 )
  {
    Pool2 = (void *)ExAllocatePool2(64, 200, 1128482904);
    if ( Pool2 )
    {
      v15 = Crashdump_Endpoint_Initialize((_DWORD)Pool2, a2, a5, 1, 0, v14, *(_QWORD *)(a5 + 64));
      if ( v15 < 0 )
      {
LABEL_19:
        ExFreePoolWithTag(Pool2, 0x43434858u);
      }
      else
      {
        *(_QWORD *)(a5 + 120) = Pool2;
        if ( a3 )
        {
          for ( j = 0; (unsigned int)j < *(_DWORD *)a3; j = (unsigned int)(j + 1) )
          {
            v18 = *(_QWORD *)(a3 + 8);
            v19 = (*(unsigned __int8 *)(v18 + 8 * j) >> 7) + 2 * (*(_BYTE *)(v18 + 8 * j) & 0x7Fu);
            v24 = (*(unsigned __int8 *)(v18 + 8 * j) >> 7) + 2 * (*(_BYTE *)(v18 + 8 * j) & 0x7F);
            v20 = (unsigned int)v19;
            if ( !*(_QWORD *)(v10 + 8 * v19 + 176) )
              return (unsigned int)-1073741811;
            v21 = ExAllocatePool2(64, 200, 1128482904);
            Pool2 = (void *)v21;
            if ( !v21 )
              return (unsigned int)-1073741670;
            v15 = Crashdump_Endpoint_Initialize(
                    v21,
                    a2,
                    a5,
                    v24,
                    *(_DWORD *)(v18 + 8 * j + 4),
                    v23,
                    *(_QWORD *)(a5 + 64));
            if ( v15 < 0 )
              goto LABEL_19;
            *(_QWORD *)(a5 + 8 * v20 + 112) = Pool2;
          }
        }
      }
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140051d9c  mov     [rsp+arg_10], rbx
0x140051da1  mov     [rsp+arg_8], rdx
0x140051da6  push    rbp
0x140051da7  push    rsi
0x140051da8  push    rdi
0x140051da9  push    r12
0x140051dab  push    r13
0x140051dad  push    r14
0x140051daf  push    r15
0x140051db1  sub     rsp, 50h
0x140051db5  mov     r13d, 1
0x140051dbb  mov     rbp, r9
0x140051dbe  mov     edi, r13d
0x140051dc1  mov     r15, r8
0x140051dc4  mov     r12, rdx
0x140051dc7  mov     r14, rcx
0x140051dca  cmp     edi, [r14+60h]
0x140051dce  ja      loc_140051FA5
0x140051dd4  mov     rcx, r14
0x140051dd7  call    XilDeviceSlot_GetUsbDeviceHandleArray
0x140051ddc  mov     ecx, edi
0x140051dde  mov     rsi, [rax+rcx*8]
0x140051de2  test    rsi, rsi
0x140051de5  jz      short loc_140051E11
0x140051de7  mov     eax, [rsi+24h]
0x140051dea  cmp     eax, [rbp+4]
0x140051ded  jnz     short loc_140051E11
0x140051def  mov     ebx, eax
0x140051df1  lea     rdx, [rbp+0Ch]; Source2
0x140051df5  shl     rbx, 2
0x140051df9  lea     rcx, [rsi+2Ch]; Source1
0x140051dfd  mov     r8, rbx; Length
0x140051e00  call    cs:__imp_RtlCompareMemory
0x140051e07  nop     dword ptr [rax+rax+00h]
0x140051e0c  cmp     rax, rbx
0x140051e0f  jz      short loc_140051E16
0x140051e11  add     edi, r13d
0x140051e14  jmp     short loc_140051DCA
0x140051e16  mov     al, [rsi+299h]
0x140051e1c  neg     al
0x140051e1e  sbb     rcx, rcx
0x140051e21  and     ecx, 8
0x140051e24  add     rcx, 268h
0x140051e2b  add     rcx, rsi
0x140051e2e  call    XilCoreUsbDevice_GetDeviceContextBufferVA
0x140051e33  mov     ecx, [rbp+4]
0x140051e36  mov     r8, r15
0x140051e39  mov     rbp, [rsp+88h+arg_20]
0x140051e41  mov     rdx, r12
0x140051e44  mov     r9b, [rsi+8Fh]
0x140051e4b  mov     r14, rax
0x140051e4e  mov     dword ptr [rsp+88h+var_58], ecx
0x140051e52  mov     rcx, rbp
0x140051e55  mov     [rsp+88h+var_60], rsi
0x140051e5a  mov     [rsp+88h+var_48], rax
0x140051e5f  mov     [rsp+88h+var_68], rax
0x140051e64  call    Crashdump_UsbDevice_Initialize
0x140051e69  mov     ebx, eax
0x140051e6b  test    eax, eax
0x140051e6d  js      loc_140051FAA
0x140051e73  mov     edx, 0C8h
0x140051e78  mov     ecx, 40h ; '@'
0x140051e7d  mov     r8d, 43434858h
0x140051e83  call    cs:__imp_ExAllocatePool2
0x140051e8a  nop     dword ptr [rax+rax+00h]
0x140051e8f  mov     rdi, rax
0x140051e92  test    rax, rax
0x140051e95  jnz     short loc_140051EA1
0x140051e97  mov     ebx, 0C000009Ah
0x140051e9c  jmp     loc_140051FAA
0x140051ea1  mov     rax, [rbp+40h]
0x140051ea5  mov     r9d, r13d
0x140051ea8  mov     [rsp+88h+var_58], rax
0x140051ead  mov     r8, rbp
0x140051eb0  mov     [rsp+88h+var_60], r14
0x140051eb5  mov     rdx, r12
0x140051eb8  mov     rcx, rdi
0x140051ebb  mov     dword ptr [rsp+88h+var_68], 0
0x140051ec3  call    Crashdump_Endpoint_Initialize
0x140051ec8  mov     ebx, eax
0x140051eca  test    eax, eax
0x140051ecc  js      loc_140051F8F
0x140051ed2  mov     [rbp+78h], rdi
0x140051ed6  test    r15, r15
0x140051ed9  jz      loc_140051FAA
0x140051edf  xor     r14d, r14d
0x140051ee2  cmp     r14d, [r15]
0x140051ee5  jnb     loc_140051FAA
0x140051eeb  mov     r13, [r15+8]
0x140051eef  movzx   ecx, byte ptr [r13+r14*8+0]
0x140051ef5  mov     eax, ecx
0x140051ef7  shr     ecx, 7
0x140051efa  btr     eax, 7
0x140051efe  lea     eax, [rcx+rax*2]
0x140051f01  cmp     qword ptr [rsi+rax*8+0B0h], 0
0x140051f0a  mov     [rsp+88h+arg_0], eax
0x140051f11  mov     r12d, eax
0x140051f14  jz      short loc_140051F88
0x140051f16  mov     edx, 0C8h
0x140051f1b  mov     ecx, 40h ; '@'
0x140051f20  mov     r8d, 43434858h
0x140051f26  call    cs:__imp_ExAllocatePool2
0x140051f2d  nop     dword ptr [rax+rax+00h]
0x140051f32  mov     rdi, rax
0x140051f35  test    rax, rax
0x140051f38  jz      loc_140051E97
0x140051f3e  mov     rax, [rbp+40h]
0x140051f42  mov     r8, rbp
0x140051f45  mov     r9d, [rsp+88h+arg_0]
0x140051f4d  mov     rcx, rdi
0x140051f50  mov     rdx, [rsp+88h+arg_8]
0x140051f58  mov     [rsp+88h+var_58], rax
0x140051f5d  mov     rax, [rsp+88h+var_48]
0x140051f62  mov     [rsp+88h+var_60], rax
0x140051f67  mov     eax, [r13+r14*8+4]
0x140051f6c  mov     dword ptr [rsp+88h+var_68], eax
0x140051f70  call    Crashdump_Endpoint_Initialize
0x140051f75  mov     ebx, eax
0x140051f77  test    eax, eax
0x140051f79  js      short loc_140051F8F
0x140051f7b  mov     [rbp+r12*8+70h], rdi
0x140051f80  inc     r14d
0x140051f83  jmp     loc_140051EE2
0x140051f88  mov     ebx, 0C000000Dh
0x140051f8d  jmp     short loc_140051FAA
0x140051f8f  mov     edx, 43434858h; Tag
0x140051f94  mov     rcx, rdi; P
0x140051f97  call    cs:__imp_ExFreePoolWithTag
0x140051f9e  nop     dword ptr [rax+rax+00h]
0x140051fa3  jmp     short loc_140051FAA
0x140051fa5  mov     ebx, 0C0000225h
0x140051faa  mov     eax, ebx
0x140051fac  mov     rbx, [rsp+88h+arg_10]
0x140051fb4  add     rsp, 50h
0x140051fb8  pop     r15
0x140051fba  pop     r14
0x140051fbc  pop     r13
0x140051fbe  pop     r12
0x140051fc0  pop     rdi
0x140051fc1  pop     rsi
0x140051fc2  pop     rbp
0x140051fc3  retn
```
