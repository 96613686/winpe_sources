# BthUsb_ScoUrbError(_SCO_USB_TRANSFER_CTX *,_BTH_PIPE_TYPE)

- ea: `0x140005be8`
- end: `0x140005c84`
- name: `?BthUsb_ScoUrbError@@YAEPEAU_SCO_USB_TRANSFER_CTX@@W4_BTH_PIPE_TYPE@@@Z`
- size: `156`
- prototype: `unsigned __int8 __fastcall(struct _SCO_USB_TRANSFER_CTX *, enum _BTH_PIPE_TYPE)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400058bc`
- `0x1400081b0`
- `0x140009a90`

## callees

- `0x140005be8`
- `0x1400070fc`
- `0x140007218`

## pseudocode

```c
unsigned __int8 __fastcall BthUsb_ScoUrbError(struct _SCO_USB_TRANSFER_CTX *a1, enum _BTH_PIPE_TYPE a2)
{
  int Status; // r8d
  bool v3; // dl
  int v5; // r8d
  bool v6; // dl

  Status = a1->Irp->IoStatus.Status;
  if ( Status < 0 )
  {
    v3 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_sd(WPP_GLOBAL_Control->AttachedDevice, v3, Status, WPP_GLOBAL_Control->DeviceExtension);
    return 1;
  }
  v5 = a1->Urb->UrbHeader.Status;
  if ( v5 < 0 )
  {
    v6 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_sD(WPP_GLOBAL_Control->AttachedDevice, v6, v5, WPP_GLOBAL_Control->DeviceExtension);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x140005be8  sub     rsp, 58h
0x140005bec  movsxd  rax, edx
0x140005bef  lea     r9, ?PipeStrings@@3PAPEBDA; char const * near * PipeStrings
0x140005bf6  mov     r9, [r9+rax*8]
0x140005bfa  mov     rax, [rcx+40h]
0x140005bfe  mov     r8d, [rax+30h]
0x140005c02  test    r8d, r8d
0x140005c05  jns     short loc_140005C3C
0x140005c07  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c0e  mov     eax, [rcx+2Ch]
0x140005c11  test    al, 8
0x140005c13  jz      short loc_140005C1F
0x140005c15  cmp     byte ptr [rcx+29h], 2
0x140005c19  jb      short loc_140005C1F
0x140005c1b  mov     dl, 1
0x140005c1d  jmp     short loc_140005C21
0x140005c1f  xor     dl, dl
0x140005c21  mov     [rsp+58h+var_10], r8d
0x140005c26  mov     [rsp+58h+var_18], r9
0x140005c2b  mov     r9, [rcx+40h]
0x140005c2f  mov     rcx, [rcx+18h]
0x140005c33  call    WPP_RECORDER_AND_TRACE_SF_sd
0x140005c38  mov     al, 1
0x140005c3a  jmp     short loc_140005C7E
0x140005c3c  mov     rax, [rcx+48h]
0x140005c40  mov     r8d, [rax+4]
0x140005c44  test    r8d, r8d
0x140005c47  jns     short loc_140005C7C
0x140005c49  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c50  mov     eax, [rcx+2Ch]
0x140005c53  test    al, 8
0x140005c55  jz      short loc_140005C61
0x140005c57  cmp     byte ptr [rcx+29h], 2
0x140005c5b  jb      short loc_140005C61
0x140005c5d  mov     dl, 1
0x140005c5f  jmp     short loc_140005C63
0x140005c61  xor     dl, dl
0x140005c63  mov     [rsp+58h+var_10], r8d
0x140005c68  mov     [rsp+58h+var_18], r9
0x140005c6d  mov     r9, [rcx+40h]
0x140005c71  mov     rcx, [rcx+18h]
0x140005c75  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140005c7a  jmp     short loc_140005C38
0x140005c7c  xor     al, al
0x140005c7e  add     rsp, 58h
0x140005c82  retn
```
