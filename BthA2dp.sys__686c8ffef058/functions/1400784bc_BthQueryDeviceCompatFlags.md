# BthQueryDeviceCompatFlags

- ea: `0x1400784bc`
- end: `0x140078685`
- name: `BthQueryDeviceCompatFlags`
- size: `457`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14007a240`
- `0x14007aae8`

## callees

- `0x1400784bc`
- `0x140086334`
- `0x140086628`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140078606`
- `ntoskrnl!ExAllocatePool2` at `0x140078606`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078650`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078650`
- `ntoskrnl!ObfDereferenceObject` at `0x140078666`
- `ntoskrnl!ObfDereferenceObject` at `0x140078666`
- `ntoskrnl!KseQueryDeviceFlags` at `0x14007863c`
- `ntoskrnl!KseQueryDeviceFlags` at `0x14007863c`

## string_xrefs

- `0x140078540`: `BthCodService`

## pseudocode

```c
__int64 __fastcall BthQueryDeviceCompatFlags(__int64 a1, int a2, struct _DEVICE_OBJECT *a3)
{
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  const wchar_t *v9; // rbx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  __int64 v16; // rdi
  __int64 Pool2; // rax
  void *v18; // rdi
  PVOID Object; // [rsp+40h] [rbp+8h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+50h] [rbp+18h] BYREF
  __int64 v22; // [rsp+58h] [rbp+20h] BYREF

  DeviceObject = a3;
  if ( a2 > 7 )
  {
    v10 = a2 - 8;
    if ( !v10 )
    {
      v9 = L"BthAvrcp";
      goto LABEL_33;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      v9 = L"BthBVRADelay";
      goto LABEL_33;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      v9 = L"BthVCTeardownDelay";
      goto LABEL_33;
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      v9 = L"BthDeviceHci";
      goto LABEL_33;
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      v9 = L"BthDeviceHfpVr";
      goto LABEL_33;
    }
    v15 = v14 - 1;
    if ( !v15 )
    {
      v9 = L"BthDeviceL2cap";
      goto LABEL_33;
    }
    if ( v15 == 1 )
    {
      v9 = L"BthDeviceHfp";
      goto LABEL_33;
    }
    goto LABEL_25;
  }
  if ( a2 == 7 )
  {
    v9 = L"BthA2DP";
    goto LABEL_33;
  }
  if ( !a2 )
  {
    v9 = L"BthCodService";
    goto LABEL_33;
  }
  v4 = a2 - 1;
  if ( !v4 )
  {
    v9 = L"BthVCDelay";
    goto LABEL_33;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v9 = L"BthIgnoreChupDelay";
    goto LABEL_33;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v9 = L"BthVirtualCalling";
    goto LABEL_33;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v9 = L"BthHfpSlcScoDelay";
    goto LABEL_33;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v9 = L"BthBrDevice";
    goto LABEL_33;
  }
  if ( v8 != 1 )
  {
LABEL_25:
    v9 = L"Unknown";
    goto LABEL_33;
  }
  v9 = L"BthLeDevice";
LABEL_33:
  v16 = -1;
  do
    ++v16;
  while ( v9[v16] );
  Object = 0;
  v22 = 0;
  if ( a1 )
  {
    if ( a3 || (int)GetBthportDeviceObject((PFILE_OBJECT *)&Object, &DeviceObject) >= 0 )
    {
      Pool2 = ExAllocatePool2(256, 2 * v16 + 276, 1128551490);
      v18 = (void *)Pool2;
      if ( Pool2 )
      {
        if ( (int)GetDeviceFingerprintString(a1, Pool2, v9, DeviceObject) >= 0 )
          KseQueryDeviceFlags(v18, v9, &v22);
        ExFreePoolWithTag(v18, 0x43445442u);
      }
    }
    if ( Object )
      ObfDereferenceObject(Object);
  }
  return v22;
}

```

## disassembly

```asm
0x1400784bc  mov     [rsp+arg_8], rbx
0x1400784c1  mov     [rsp+DeviceObject], r8
0x1400784c6  push    rbp
0x1400784c7  push    rsi
0x1400784c8  push    rdi
0x1400784c9  sub     rsp, 20h
0x1400784cd  xor     ebp, ebp
0x1400784cf  mov     rsi, rcx
0x1400784d2  cmp     edx, 7
0x1400784d5  jg      short loc_140078552
0x1400784d7  jz      short loc_140078549
0x1400784d9  test    edx, edx
0x1400784db  jz      short loc_140078540
0x1400784dd  sub     edx, 1
0x1400784e0  jz      short loc_140078537
0x1400784e2  sub     edx, 1
0x1400784e5  jz      short loc_14007852B
0x1400784e7  sub     edx, 1
0x1400784ea  jz      short loc_14007851F
0x1400784ec  sub     edx, 1
0x1400784ef  jz      short loc_140078513
0x1400784f1  sub     edx, 1
0x1400784f4  jz      short loc_140078507
0x1400784f6  cmp     edx, 1
0x1400784f9  jnz     short loc_140078575
0x1400784fb  lea     rbx, aBthledevice; "BthLeDevice"
0x140078502  jmp     loc_1400785BB
0x140078507  lea     rbx, aBthbrdevice; "BthBrDevice"
0x14007850e  jmp     loc_1400785BB
0x140078513  lea     rbx, aBthhfpslcscode; "BthHfpSlcScoDelay"
0x14007851a  jmp     loc_1400785BB
0x14007851f  lea     rbx, aBthvirtualcall; "BthVirtualCalling"
0x140078526  jmp     loc_1400785BB
0x14007852b  lea     rbx, aBthignorechupd; "BthIgnoreChupDelay"
0x140078532  jmp     loc_1400785BB
0x140078537  lea     rbx, aBthvcdelay; "BthVCDelay"
0x14007853e  jmp     short loc_1400785BB
0x140078540  lea     rbx, aBthcodservice; "BthCodService"
0x140078547  jmp     short loc_1400785BB
0x140078549  lea     rbx, aBtha2dp; "BthA2DP"
0x140078550  jmp     short loc_1400785BB
0x140078552  sub     edx, 8
0x140078555  jz      short loc_1400785B4
0x140078557  sub     edx, 1
0x14007855a  jz      short loc_1400785AB
0x14007855c  sub     edx, 1
0x14007855f  jz      short loc_1400785A2
0x140078561  sub     edx, 1
0x140078564  jz      short loc_140078599
0x140078566  sub     edx, 1
0x140078569  jz      short loc_140078590
0x14007856b  sub     edx, 1
0x14007856e  jz      short loc_140078587
0x140078570  cmp     edx, 1
0x140078573  jz      short loc_14007857E
0x140078575  lea     rbx, aUnknown; "Unknown"
0x14007857c  jmp     short loc_1400785BB
0x14007857e  lea     rbx, aBthdevicehfp; "BthDeviceHfp"
0x140078585  jmp     short loc_1400785BB
0x140078587  lea     rbx, aBthdevicel2cap; "BthDeviceL2cap"
0x14007858e  jmp     short loc_1400785BB
0x140078590  lea     rbx, aBthdevicehfpvr; "BthDeviceHfpVr"
0x140078597  jmp     short loc_1400785BB
0x140078599  lea     rbx, aBthdevicehci; "BthDeviceHci"
0x1400785a0  jmp     short loc_1400785BB
0x1400785a2  lea     rbx, aBthvcteardownd; "BthVCTeardownDelay"
0x1400785a9  jmp     short loc_1400785BB
0x1400785ab  lea     rbx, aBthbvradelay; "BthBVRADelay"
0x1400785b2  jmp     short loc_1400785BB
0x1400785b4  lea     rbx, aBthavrcp; "BthAvrcp"
0x1400785bb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400785bf  inc     rdi
0x1400785c2  cmp     [rbx+rdi*2], bp
0x1400785c6  jnz     short loc_1400785BF
0x1400785c8  mov     [rsp+38h+Object], rbp
0x1400785cd  mov     [rsp+38h+arg_18], rbp
0x1400785d2  test    rsi, rsi
0x1400785d5  jz      loc_140078672
0x1400785db  test    r8, r8
0x1400785de  jnz     short loc_1400785F3
0x1400785e0  lea     rdx, [rsp+38h+DeviceObject]; DeviceObject
0x1400785e5  lea     rcx, [rsp+38h+Object]; FileObject
0x1400785ea  call    GetBthportDeviceObject
0x1400785ef  test    eax, eax
0x1400785f1  js      short loc_14007865C
0x1400785f3  lea     rdx, ds:114h[rdi*2]
0x1400785fb  mov     ecx, 100h
0x140078600  mov     r8d, 43445442h
0x140078606  call    cs:__imp_ExAllocatePool2
0x14007860d  nop     dword ptr [rax+rax+00h]
0x140078612  mov     rdi, rax
0x140078615  test    rax, rax
0x140078618  jz      short loc_14007865C
0x14007861a  mov     r9, [rsp+38h+DeviceObject]
0x14007861f  mov     r8, rbx
0x140078622  mov     rdx, rax
0x140078625  mov     rcx, rsi
0x140078628  call    GetDeviceFingerprintString
0x14007862d  test    eax, eax
0x14007862f  js      short loc_140078648
0x140078631  lea     r8, [rsp+38h+arg_18]
0x140078636  mov     rdx, rbx
0x140078639  mov     rcx, rdi
0x14007863c  call    cs:__imp_KseQueryDeviceFlags
0x140078643  nop     dword ptr [rax+rax+00h]
0x140078648  mov     edx, 43445442h; Tag
0x14007864d  mov     rcx, rdi; P
0x140078650  call    cs:__imp_ExFreePoolWithTag
0x140078657  nop     dword ptr [rax+rax+00h]
0x14007865c  mov     rcx, [rsp+38h+Object]; Object
0x140078661  test    rcx, rcx
0x140078664  jz      short loc_140078672
0x140078666  call    cs:__imp_ObfDereferenceObject
0x14007866d  nop     dword ptr [rax+rax+00h]
0x140078672  mov     rax, [rsp+38h+arg_18]
0x140078677  mov     rbx, [rsp+38h+arg_8]
0x14007867c  add     rsp, 20h
0x140078680  pop     rdi
0x140078681  pop     rsi
0x140078682  pop     rbp
0x140078683  retn
```
