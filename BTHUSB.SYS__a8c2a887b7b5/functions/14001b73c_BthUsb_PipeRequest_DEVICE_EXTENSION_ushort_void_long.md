# BthUsb_PipeRequest(_DEVICE_EXTENSION *,ushort,void *,long)

- ea: `0x14001b73c`
- end: `0x14001b837`
- name: `?BthUsb_PipeRequest@@YAJPEAU_DEVICE_EXTENSION@@GPEAXJ@Z`
- size: `251`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, unsigned __int16, void *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140007f8c`
- `0x1400098bc`

## callees

- `0x140001924`
- `0x140006f3c`
- `0x14000e1c0`
- `0x14001b73c`
- `0x14001bd90`

## pseudocode

```c
__int64 __fastcall BthUsb_PipeRequest(struct _DEVICE_EXTENSION *a1, __int64 a2, void *a3)
{
  char v5; // bl
  bool v6; // dl
  struct _DEVICE_OBJECT *TopOfStack; // rcx
  int v8; // edx
  unsigned int v9; // edi
  _QWORD v11[25]; // [rsp+50h] [rbp-C8h] BYREF

  memset(v11, 0, 152);
  v5 = 1;
  v6 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_qH(WPP_GLOBAL_Control->AttachedDevice, v6, (_DWORD)a3, WPP_GLOBAL_Control->DeviceExtension);
  TopOfStack = a1->TopOfStack;
  LODWORD(v11[0]) = 131112;
  v11[3] = a3;
  v9 = USBCallSyncEx(TopOfStack, (unsigned __int64)v11, 100, &a1->RemoveLock);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v5 = 0;
  LOBYTE(v8) = v5;
  WPP_RECORDER_AND_TRACE_SF_qD(
    WPP_GLOBAL_Control->AttachedDevice,
    v8,
    (_DWORD)WPP_GLOBAL_Control,
    WPP_GLOBAL_Control->DeviceExtension);
  return v9;
}

```

## disassembly

```asm
0x14001b73c  push    rbx
0x14001b73e  push    rbp
0x14001b73f  push    rsi
0x14001b740  push    rdi
0x14001b741  push    r12
0x14001b743  sub     rsp, 0F0h
0x14001b74a  mov     rsi, r8
0x14001b74d  mov     rdi, rcx
0x14001b750  xor     eax, eax
0x14001b752  lea     rcx, [rsp+118h+var_C8+2]; void *
0x14001b757  mov     r8d, 96h; Size
0x14001b75d  mov     word ptr [rsp+118h+var_C8], ax
0x14001b762  xor     edx, edx; Val
0x14001b764  call    memset
0x14001b769  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b770  mov     bl, 1
0x14001b772  mov     eax, [rcx+2Ch]
0x14001b775  test    al, 4
0x14001b777  jz      short loc_14001B783
0x14001b779  cmp     byte ptr [rcx+29h], 4
0x14001b77d  jb      short loc_14001B783
0x14001b77f  mov     dl, bl
0x14001b781  jmp     short loc_14001B785
0x14001b783  xor     dl, dl
0x14001b785  mov     r9, [rcx+40h]
0x14001b789  lea     r12, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001b790  mov     rcx, [rcx+18h]
0x14001b794  mov     ebp, 2
0x14001b799  mov     word ptr [rsp+118h+var_D0], bp
0x14001b79e  mov     [rsp+118h+var_D8], rsi
0x14001b7a3  mov     [rsp+118h+var_E0], r12
0x14001b7a8  mov     [rsp+118h+var_E8], 40h ; '@'
0x14001b7af  mov     [rsp+118h+var_F0], 3
0x14001b7b7  call    WPP_RECORDER_AND_TRACE_SF_qH
0x14001b7bc  mov     rcx, [rdi+28h]; Tag
0x14001b7c0  lea     r9, [rdi+30h]
0x14001b7c4  lea     r8d, [rbp+62h]
0x14001b7c8  mov     [rsp+118h+var_C8], 20028h
0x14001b7d0  lea     rdx, [rsp+118h+var_C8]
0x14001b7d5  mov     [rsp+118h+var_B0], rsi
0x14001b7da  call    USBCallSyncEx
0x14001b7df  mov     edi, eax
0x14001b7e1  mov     r8, cs:WPP_GLOBAL_Control
0x14001b7e8  mov     ecx, [r8+2Ch]
0x14001b7ec  test    cl, 4
0x14001b7ef  jz      short loc_14001B7F8
0x14001b7f1  cmp     byte ptr [r8+29h], 4
0x14001b7f6  jnb     short loc_14001B7FA
0x14001b7f8  xor     bl, bl
0x14001b7fa  mov     r9, [r8+40h]
0x14001b7fe  mov     dl, bl
0x14001b800  mov     rcx, [r8+18h]
0x14001b804  mov     [rsp+118h+var_D0], edi
0x14001b808  mov     [rsp+118h+var_D8], rsi
0x14001b80d  mov     [rsp+118h+var_E0], r12
0x14001b812  mov     [rsp+118h+var_E8], 41h ; 'A'
0x14001b819  mov     [rsp+118h+var_F0], 3
0x14001b821  call    WPP_RECORDER_AND_TRACE_SF_qD
0x14001b826  mov     eax, edi
0x14001b828  add     rsp, 0F0h
0x14001b82f  pop     r12
0x14001b831  pop     rdi
0x14001b832  pop     rsi
0x14001b833  pop     rbp
0x14001b834  pop     rbx
0x14001b835  retn
```
