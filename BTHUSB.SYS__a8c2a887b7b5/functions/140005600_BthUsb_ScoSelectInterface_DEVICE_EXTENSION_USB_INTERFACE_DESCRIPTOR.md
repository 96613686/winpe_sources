# BthUsb_ScoSelectInterface(_DEVICE_EXTENSION *,_USB_INTERFACE_DESCRIPTOR *)

- ea: `0x140005600`
- end: `0x1400056e1`
- name: `?BthUsb_ScoSelectInterface@@YAJPEAU_DEVICE_EXTENSION@@PEAU_USB_INTERFACE_DESCRIPTOR@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _USB_INTERFACE_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400030e0`
- `0x140005180`

## callees

- `0x1400017d4`
- `0x140002dcc`
- `0x140005600`
- `0x14000ae54`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoSelectInterface(
        struct _DEVICE_EXTENSION *a1,
        struct _USB_INTERFACE_DESCRIPTOR *a2,
        int a3)
{
  struct _USB_INTERFACE_DESCRIPTOR *OffInterface; // rbx
  char v5; // si
  int v6; // edx
  int v7; // ebp
  int v8; // r8d

  OffInterface = a2;
  if ( !a2 )
    OffInterface = a1->Sco.OffInterface;
  v5 = 1;
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)a2, a3, WPP_GLOBAL_Control->DeviceExtension);
  v7 = BthUsb_SelectIsoInterface(a1, OffInterface);
  if ( v7 >= 0 )
  {
    a1->Sco.CurInterface = OffInterface;
    v7 = 0;
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v5 = 0;
  LOBYTE(v6) = v5;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    v6,
    v8,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    94,
    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
    v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140005600  push    rbx
0x140005602  push    rbp
0x140005603  push    rsi
0x140005604  push    rdi
0x140005605  push    r15
0x140005607  sub     rsp, 60h
0x14000560b  mov     rbx, rdx
0x14000560e  mov     rdi, rcx
0x140005611  test    rdx, rdx
0x140005614  jnz     short loc_14000561D
0x140005616  mov     rbx, [rcx+280h]
0x14000561d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005624  mov     sil, 1
0x140005627  mov     eax, [rcx+2Ch]
0x14000562a  test    al, 8
0x14000562c  jz      short loc_140005639
0x14000562e  cmp     byte ptr [rcx+29h], 4
0x140005632  jb      short loc_140005639
0x140005634  mov     dl, sil
0x140005637  jmp     short loc_14000563B
0x140005639  xor     dl, dl
0x14000563b  movzx   eax, byte ptr [rbx+3]
0x14000563f  lea     r15, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140005646  mov     r9, [rcx+40h]
0x14000564a  mov     rcx, [rcx+18h]
0x14000564e  mov     [rsp+88h+var_38], eax
0x140005652  mov     [rsp+88h+var_40], rbx
0x140005657  mov     [rsp+88h+var_48], rdi
0x14000565c  mov     [rsp+88h+var_50], r15
0x140005661  mov     [rsp+88h+var_58], 5Dh ; ']'
0x140005668  mov     [rsp+88h+var_60], 4
0x140005670  call    WPP_RECORDER_AND_TRACE_SF_qqD
0x140005675  mov     rdx, rbx; struct _USB_INTERFACE_DESCRIPTOR *
0x140005678  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14000567b  call    ?BthUsb_SelectIsoInterface@@YAJPEAU_DEVICE_EXTENSION@@PEAU_USB_INTERFACE_DESCRIPTOR@@K@Z; BthUsb_SelectIsoInterface(_DEVICE_EXTENSION *,_USB_INTERFACE_DESCRIPTOR *,ulong)
0x140005680  mov     ebp, eax
0x140005682  test    eax, eax
0x140005684  js      short loc_14000568F
0x140005686  mov     [rdi+298h], rbx
0x14000568d  xor     ebp, ebp
0x14000568f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005696  mov     eax, [rcx+2Ch]
0x140005699  test    al, 8
0x14000569b  jz      short loc_1400056A3
0x14000569d  cmp     byte ptr [rcx+29h], 4
0x1400056a1  jnb     short loc_1400056A6
0x1400056a3  xor     sil, sil
0x1400056a6  mov     r9, [rcx+40h]
0x1400056aa  mov     dl, sil
0x1400056ad  mov     rcx, [rcx+18h]
0x1400056b1  mov     dword ptr [rsp+88h+var_48], ebp
0x1400056b5  mov     [rsp+88h+var_50], r15
0x1400056ba  mov     [rsp+88h+var_58], 5Eh ; '^'
0x1400056c1  mov     [rsp+88h+var_60], 4
0x1400056c9  mov     [rsp+88h+var_68], 4
0x1400056ce  call    WPP_RECORDER_AND_TRACE_SF_D
0x1400056d3  mov     eax, ebp
0x1400056d5  add     rsp, 60h
0x1400056d9  pop     r15
0x1400056db  pop     rdi
0x1400056dc  pop     rsi
0x1400056dd  pop     rbp
0x1400056de  pop     rbx
0x1400056df  retn
```
