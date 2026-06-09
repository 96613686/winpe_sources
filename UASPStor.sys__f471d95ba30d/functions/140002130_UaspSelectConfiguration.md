# UaspSelectConfiguration

- ea: `0x140002130`
- end: `0x140002318`
- name: `UaspSelectConfiguration`
- size: `488`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400015cc`

## callees

- `0x140001ec8`
- `0x140002130`
- `0x14000607c`
- `0x14000d900`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400022df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400022f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400022df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400022f5`
- `ntoskrnl!ExAllocatePool2` at `0x140002184`
- `ntoskrnl!ExAllocatePool2` at `0x1400022ad`
- `ntoskrnl!ExAllocatePool2` at `0x140002184`
- `ntoskrnl!ExAllocatePool2` at `0x1400022ad`
- `USBD!USBD_CreateConfigurationRequestEx` at `0x14000225a`
- `USBD!USBD_CreateConfigurationRequestEx` at `0x14000225a`

## pseudocode

```c
__int64 __fastcall UaspSelectConfiguration(__int64 a1, __int64 a2, __int64 a3)
{
  struct _USB_CONFIGURATION_DESCRIPTOR *v3; // rdi
  __int64 v6; // rcx
  struct _USBD_INTERFACE_LIST_ENTRY *Pool2; // r15
  int v8; // ebx
  struct _USB_INTERFACE_DESCRIPTOR *v9; // r9
  char v10; // cl
  char v11; // dl
  char v12; // r8
  __int16 v13; // ax
  bool v14; // cf
  PURB ConfigurationRequest; // rax
  _QWORD *p_Length; // rdi
  void *v17; // rax
  unsigned __int16 *v18; // r14
  char v20[4]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-Ch] BYREF
  struct _USB_INTERFACE_DESCRIPTOR *v22; // [rsp+48h] [rbp-8h] BYREF
  char v23; // [rsp+80h] [rbp+30h] BYREF
  __int64 v24; // [rsp+88h] [rbp+38h] BYREF
  char v25; // [rsp+98h] [rbp+48h] BYREF

  v24 = a2;
  v3 = *(struct _USB_CONFIGURATION_DESCRIPTOR **)(a1 + 40);
  LOBYTE(v24) = -1;
  v23 = -1;
  v25 = -1;
  v20[0] = -1;
  v22 = 0;
  v21 = 0;
  Pool2 = (struct _USBD_INTERFACE_LIST_ENTRY *)ExAllocatePool2(256, 32, 1969320816);
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  UaspParseConfigurationDescriptor(v6, *(unsigned __int8 **)(a1 + 40), &v22, &v24, &v23, &v25, v20, &v21);
  v9 = v22;
  if ( !v22 || (_BYTE)v24 == 0xFF || (v10 = v23, v23 == -1) || (v11 = v25, v25 == -1) || (v12 = v20[0], v20[0] == -1) )
  {
    p_Length = 0;
    v8 = -1073741435;
  }
  else
  {
    *(_BYTE *)(a1 + 1088) = v24;
    v13 = -1;
    v14 = v21 < 0xFFFF;
    *(_BYTE *)(a1 + 1089) = v10;
    if ( v14 )
      v13 = v21;
    *(_BYTE *)(a1 + 1090) = v11;
    *(_WORD *)(a1 + 1280) = v13;
    *(_BYTE *)(a1 + 1091) = v12;
    *(_QWORD *)(a1 + 48) = v9;
    Pool2->InterfaceDescriptor = v9;
    Pool2[1].InterfaceDescriptor = 0;
    v3->bNumInterfaces = 1;
    ConfigurationRequest = USBD_CreateConfigurationRequestEx(v3, Pool2);
    p_Length = &ConfigurationRequest->UrbHeader.Length;
    if ( !ConfigurationRequest )
      goto LABEL_11;
    v8 = UaspSyncSendUsbRequestNew(0, a3, ConfigurationRequest, 0);
    if ( v8 >= 0 )
    {
      v17 = *(void **)(a1 + 72);
      v18 = (unsigned __int16 *)(p_Length + 5);
      *(_QWORD *)(a1 + 64) = p_Length[4];
      if ( !v17 )
      {
        v17 = (void *)ExAllocatePool2(64, *v18, 1969320816);
        *(_QWORD *)(a1 + 72) = v17;
        if ( !v17 )
        {
LABEL_11:
          v8 = -1073741670;
          goto LABEL_17;
        }
      }
      memmove(v17, p_Length + 5, *v18);
    }
  }
LABEL_17:
  ExFreePoolWithTag(Pool2, 0);
  if ( p_Length )
    ExFreePoolWithTag(p_Length, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140002130  mov     [rsp-28h+arg_10], rbx
0x140002135  mov     [rsp-28h+arg_8], rdx
0x14000213a  push    rbp
0x14000213b  push    rsi
0x14000213c  push    rdi
0x14000213d  push    r14
0x14000213f  push    r15
0x140002141  mov     rbp, rsp
0x140002144  sub     rsp, 50h
0x140002148  mov     rdi, [rcx+28h]
0x14000214c  mov     r14b, 0FFh
0x14000214f  mov     rbx, r8
0x140002152  mov     byte ptr [rbp+arg_8], r14b
0x140002156  mov     rsi, rcx
0x140002159  mov     [rbp+arg_0], r14b
0x14000215d  mov     ecx, 100h
0x140002162  mov     [rbp+arg_18], r14b
0x140002166  mov     r8d, 75617370h
0x14000216c  mov     [rbp+var_10], r14b
0x140002170  mov     edx, 20h ; ' '
0x140002175  mov     [rbp+var_8], 0
0x14000217d  mov     [rbp+var_C], 0
0x140002184  call    cs:__imp_ExAllocatePool2
0x14000218b  nop     dword ptr [rax+rax+00h]
0x140002190  mov     r15, rax
0x140002193  test    rax, rax
0x140002196  jnz     short loc_1400021A2
0x140002198  mov     ebx, 0C000009Ah
0x14000219d  jmp     loc_140002301
0x1400021a2  mov     rdx, [rsi+28h]
0x1400021a6  lea     rax, [rbp+var_C]
0x1400021aa  mov     [rsp+50h+var_18], rax
0x1400021af  lea     r9, [rbp+arg_8]
0x1400021b3  lea     rax, [rbp+var_10]
0x1400021b7  mov     [rsp+50h+var_20], rax
0x1400021bc  lea     r8, [rbp+var_8]
0x1400021c0  lea     rax, [rbp+arg_18]
0x1400021c4  mov     [rsp+50h+var_28], rax
0x1400021c9  lea     rax, [rbp+arg_0]
0x1400021cd  mov     [rsp+50h+var_30], rax
0x1400021d2  call    UaspParseConfigurationDescriptor
0x1400021d7  mov     r9, [rbp+var_8]
0x1400021db  test    r9, r9
0x1400021de  jz      loc_1400022D3
0x1400021e4  mov     al, byte ptr [rbp+arg_8]
0x1400021e7  cmp     al, r14b
0x1400021ea  jz      loc_1400022D3
0x1400021f0  mov     cl, [rbp+arg_0]
0x1400021f3  cmp     cl, r14b
0x1400021f6  jz      loc_1400022D3
0x1400021fc  mov     dl, [rbp+arg_18]
0x1400021ff  cmp     dl, r14b
0x140002202  jz      loc_1400022D3
0x140002208  mov     r8b, [rbp+var_10]
0x14000220c  cmp     r8b, r14b
0x14000220f  jz      loc_1400022D3
0x140002215  mov     [rsi+440h], al
0x14000221b  mov     eax, 0FFFFh
0x140002220  cmp     [rbp+var_C], eax
0x140002223  mov     [rsi+441h], cl
0x140002229  mov     rcx, rdi; ConfigurationDescriptor
0x14000222c  cmovb   eax, [rbp+var_C]
0x140002230  mov     [rsi+442h], dl
0x140002236  mov     rdx, r15; InterfaceList
0x140002239  mov     [rsi+500h], ax
0x140002240  mov     [rsi+443h], r8b
0x140002247  mov     [rsi+30h], r9
0x14000224b  mov     [r15], r9
0x14000224e  mov     qword ptr [r15+10h], 0
0x140002256  mov     byte ptr [rdi+4], 1
0x14000225a  call    cs:__imp_USBD_CreateConfigurationRequestEx
0x140002261  nop     dword ptr [rax+rax+00h]
0x140002266  mov     rdi, rax
0x140002269  test    rax, rax
0x14000226c  jnz     short loc_140002275
0x14000226e  mov     ebx, 0C000009Ah
0x140002273  jmp     short loc_1400022DA
0x140002275  xor     r9d, r9d
0x140002278  mov     r8, rdi
0x14000227b  mov     rdx, rbx
0x14000227e  xor     ecx, ecx
0x140002280  call    UaspSyncSendUsbRequestNew
0x140002285  mov     ebx, eax
0x140002287  test    eax, eax
0x140002289  js      short loc_1400022DA
0x14000228b  mov     rax, [rsi+48h]
0x14000228f  lea     r14, [rdi+28h]
0x140002293  mov     rcx, [rdi+20h]
0x140002297  mov     [rsi+40h], rcx
0x14000229b  test    rax, rax
0x14000229e  jnz     short loc_1400022C2
0x1400022a0  movzx   edx, word ptr [r14]
0x1400022a4  lea     ecx, [rax+40h]
0x1400022a7  mov     r8d, 75617370h
0x1400022ad  call    cs:__imp_ExAllocatePool2
0x1400022b4  nop     dword ptr [rax+rax+00h]
0x1400022b9  mov     [rsi+48h], rax
0x1400022bd  test    rax, rax
0x1400022c0  jz      short loc_14000226E
0x1400022c2  movzx   r8d, word ptr [r14]; Size
0x1400022c6  mov     rdx, r14; Src
0x1400022c9  mov     rcx, rax; void *
0x1400022cc  call    memmove
0x1400022d1  jmp     short loc_1400022DA
0x1400022d3  xor     edi, edi
0x1400022d5  mov     ebx, 0C0000185h
0x1400022da  xor     edx, edx; Tag
0x1400022dc  mov     rcx, r15; P
0x1400022df  call    cs:__imp_ExFreePoolWithTag
0x1400022e6  nop     dword ptr [rax+rax+00h]
0x1400022eb  test    rdi, rdi
0x1400022ee  jz      short loc_140002301
0x1400022f0  xor     edx, edx; Tag
0x1400022f2  mov     rcx, rdi; P
0x1400022f5  call    cs:__imp_ExFreePoolWithTag
0x1400022fc  nop     dword ptr [rax+rax+00h]
0x140002301  mov     eax, ebx
0x140002303  mov     rbx, [rsp+50h+arg_10]
0x14000230b  add     rsp, 50h
0x14000230f  pop     r15
0x140002311  pop     r14
0x140002313  pop     rdi
0x140002314  pop     rsi
0x140002315  pop     rbp
0x140002316  retn
```
