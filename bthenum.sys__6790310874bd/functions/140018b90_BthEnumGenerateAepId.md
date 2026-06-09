# BthEnumGenerateAepId

- ea: `0x140018b90`
- end: `0x140018d4e`
- name: `BthEnumGenerateAepId`
- size: `446`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140019058`
- `0x14001aaac`

## callees

- `0x140001294`
- `0x140001328`
- `0x1400013e8`
- `0x140018b90`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x140018d1e`
- `ntoskrnl!ExFreePool` at `0x140018d1e`
- `ntoskrnl!ExAllocatePool2` at `0x140018bca`
- `ntoskrnl!ExAllocatePool2` at `0x140018bca`

## pseudocode

```c
__int64 __fastcall BthEnumGenerateAepId(__int64 a1, wchar_t **a2)
{
  __int64 v2; // rax
  __int64 v4; // rdi
  int v5; // edx
  wchar_t *Pool2; // r13
  NTSTATUS v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // edx
  __int64 v12; // [rsp+28h] [rbp-A0h]

  v2 = *(_QWORD *)(a1 + 8);
  *a2 = 0;
  v4 = *(_QWORD *)(v2 + 64);
  Pool2 = (wchar_t *)ExAllocatePool2(256, 110, 1330467906);
  if ( Pool2 )
  {
    v8 = *(_QWORD *)(a1 + 192);
    v9 = *(_QWORD *)(v4 + 320);
    v7 = RtlStringCchPrintfW(
           Pool2,
           0x37u,
           L"Bluetooth#Bluetooth%02.2x:%02.2x:%02.2x:%02.2x:%02.2x:%02.2x-%02.2x:%02.2x:%02.2x:%02.2x:%02.2x:%02.2x",
           BYTE5(v9),
           BYTE4(v9),
           BYTE3(v9),
           BYTE2(v9),
           BYTE1(v9),
           (unsigned __int8)v9,
           BYTE5(v8),
           BYTE4(v8),
           BYTE3(v8),
           BYTE2(v8),
           BYTE1(v8),
           (unsigned __int8)v8);
    if ( v7 >= 0 )
    {
      *a2 = Pool2;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v12) = v7;
        WPP_RECORDER_SF_d(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          v10,
          3u,
          0x19u,
          (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
          v12);
      }
      ExFreePool(Pool2);
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        3,
        24,
        (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids);
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140018b90  mov     [rsp+arg_8], rdx
0x140018b95  push    rbx
0x140018b96  push    rbp
0x140018b97  push    rsi
0x140018b98  push    rdi
0x140018b99  push    r12
0x140018b9b  push    r13
0x140018b9d  push    r14
0x140018b9f  push    r15
0x140018ba1  sub     rsp, 88h
0x140018ba8  mov     rax, [rcx+8]
0x140018bac  mov     rbx, rcx
0x140018baf  mov     qword ptr [rdx], 0
0x140018bb6  mov     ecx, 100h
0x140018bbb  mov     edx, 6Eh ; 'n'
0x140018bc0  mov     r8d, 4F4D5442h
0x140018bc6  mov     rdi, [rax+40h]
0x140018bca  call    cs:__imp_ExAllocatePool2
0x140018bd1  nop     dword ptr [rax+rax+00h]
0x140018bd6  mov     r13, rax
0x140018bd9  test    rax, rax
0x140018bdc  jnz     short loc_140018C1C
0x140018bde  lea     rax, WPP_RECORDER_INITIALIZED
0x140018be5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018bec  jz      short loc_140018C12
0x140018bee  mov     rcx, cs:WPP_GLOBAL_Control
0x140018bf5  lea     rax, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x140018bfc  lea     r9d, [r13+18h]
0x140018c00  mov     [rsp+0C8h+var_A8], rax
0x140018c05  lea     r8d, [r13+3]
0x140018c09  mov     rcx, [rcx+40h]
0x140018c0d  call    WPP_RECORDER_SF_
0x140018c12  mov     ebx, 0C000009Ah
0x140018c17  jmp     loc_140018D37
0x140018c1c  mov     rax, [rbx+0C0h]
0x140018c23  mov     rcx, [rdi+140h]
0x140018c2a  mov     rdx, rax
0x140018c2d  movzx   r12d, al
0x140018c31  shr     rdx, 8
0x140018c35  movzx   r15d, dl
0x140018c39  mov     rdx, rax
0x140018c3c  mov     [rsp+0C8h+var_58], r12d
0x140018c41  mov     [rsp+0C8h+var_60], r15d
0x140018c46  shr     rdx, 10h
0x140018c4a  movzx   r14d, dl
0x140018c4e  mov     rdx, rax
0x140018c51  mov     [rsp+0C8h+var_68], r14d
0x140018c56  shr     rdx, 18h
0x140018c5a  movzx   ebp, dl
0x140018c5d  mov     rdx, rax
0x140018c60  shr     rax, 28h
0x140018c64  movzx   ebx, al
0x140018c67  mov     rax, rcx
0x140018c6a  shr     rax, 8
0x140018c6e  movzx   r11d, al
0x140018c72  mov     rax, rcx
0x140018c75  mov     [rsp+0C8h+var_70], ebp
0x140018c79  shr     rax, 10h
0x140018c7d  movzx   r10d, al
0x140018c81  mov     rax, rcx
0x140018c84  shr     rdx, 20h
0x140018c88  shr     rax, 18h
0x140018c8c  movzx   r8d, al
0x140018c90  mov     rax, rcx
0x140018c93  movzx   esi, dl
0x140018c96  mov     [rsp+0C8h+var_78], esi
0x140018c9a  mov     [rsp+0C8h+var_80], ebx
0x140018c9e  movzx   edi, cl
0x140018ca1  mov     [rsp+0C8h+var_88], edi
0x140018ca5  mov     [rsp+0C8h+var_90], r11d
0x140018caa  shr     rcx, 28h
0x140018cae  mov     [rsp+0C8h+var_98], r10d
0x140018cb3  mov     dword ptr [rsp+0C8h+var_A0], r8d
0x140018cb8  lea     r8, aBluetoothBluet; "Bluetooth#Bluetooth%02.2x:%02.2x:%02.2x"...
0x140018cbf  shr     rax, 20h
0x140018cc3  movzx   edx, al
0x140018cc6  mov     dword ptr [rsp+0C8h+var_A8], edx
0x140018cca  mov     edx, 37h ; '7'; cchDest
0x140018ccf  movzx   r9d, cl
0x140018cd3  mov     rcx, r13; pszDest
0x140018cd6  call    RtlStringCchPrintfW
0x140018cdb  mov     ebx, eax
0x140018cdd  test    eax, eax
0x140018cdf  jns     short loc_140018D2C
0x140018ce1  lea     rax, WPP_RECORDER_INITIALIZED
0x140018ce8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018cef  jz      short loc_140018D1B
0x140018cf1  mov     rcx, cs:WPP_GLOBAL_Control
0x140018cf8  lea     rax, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x140018cff  mov     r9d, 19h
0x140018d05  mov     dword ptr [rsp+0C8h+var_A0], ebx
0x140018d09  mov     [rsp+0C8h+var_A8], rax
0x140018d0e  mov     rcx, [rcx+40h]
0x140018d12  lea     r8d, [r9-16h]
0x140018d16  call    WPP_RECORDER_SF_d
0x140018d1b  mov     rcx, r13; P
0x140018d1e  call    cs:__imp_ExFreePool
0x140018d25  nop     dword ptr [rax+rax+00h]
0x140018d2a  jmp     short loc_140018D37
0x140018d2c  mov     rax, [rsp+0C8h+arg_8]
0x140018d34  mov     [rax], r13
0x140018d37  mov     eax, ebx
0x140018d39  add     rsp, 88h
0x140018d40  pop     r15
0x140018d42  pop     r14
0x140018d44  pop     r13
0x140018d46  pop     r12
0x140018d48  pop     rdi
0x140018d49  pop     rsi
0x140018d4a  pop     rbp
0x140018d4b  pop     rbx
0x140018d4c  retn
```
