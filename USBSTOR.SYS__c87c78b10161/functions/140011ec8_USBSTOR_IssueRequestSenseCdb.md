# USBSTOR_IssueRequestSenseCdb

- ea: `0x140011ec8`
- end: `0x140011fa6`
- name: `USBSTOR_IssueRequestSenseCdb`
- size: `222`
- prototype: `__int64 __fastcall(PVOID Object, PIRP Irp, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140006ff0`
- `0x140009860`
- `0x140012730`

## callees

- `0x14000d8cc`
- `0x1400105e8`
- `0x140010664`
- `0x140011ec8`

## pseudocode

```c
__int64 __fastcall USBSTOR_IssueRequestSenseCdb(_QWORD *Object, PIRP Irp, void *a3)
{
  __int64 v6; // rcx
  PIO_SECURITY_CONTEXT SecurityContext; // rax
  char v8; // al
  int v9; // eax
  unsigned int v10; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x73u,
      (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  v6 = Object[8];
  SecurityContext = Irp->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  *(_QWORD *)(v6 + 1194) = 0;
  *(_DWORD *)(v6 + 1202) = 0;
  *(_BYTE *)(v6 + 1194) = 3;
  if ( a3 )
    v8 = 18;
  else
    v8 = BYTE3(SecurityContext->AccessState);
  *(_BYTE *)(v6 + 1198) = v8;
  v9 = USBSTOR_IssueControlRequest(
         Object,
         Irp,
         12,
         v6 + 1194,
         (IO_COMPLETION_ROUTINE *)USBSTOR_RequestSenseCdbCompletion,
         a3);
  v10 = v9;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x74u,
      (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
      v9);
  }
  return v10;
}

```

## disassembly

```asm
0x140011ec8  push    rbx
0x140011eca  push    rbp
0x140011ecb  push    rsi
0x140011ecc  push    rdi
0x140011ecd  sub     rsp, 38h
0x140011ed1  mov     rbx, r8
0x140011ed4  mov     rdi, rdx
0x140011ed7  mov     rsi, rcx
0x140011eda  mov     rcx, cs:WPP_GLOBAL_Control
0x140011ee1  lea     rbp, WPP_GLOBAL_Control
0x140011ee8  cmp     rcx, rbp
0x140011eeb  jz      short loc_140011F0F
0x140011eed  mov     eax, [rcx+2Ch]
0x140011ef0  test    al, 1
0x140011ef2  jz      short loc_140011F0F
0x140011ef4  cmp     byte ptr [rcx+29h], 5
0x140011ef8  jb      short loc_140011F0F
0x140011efa  mov     rcx, [rcx+18h]
0x140011efe  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140011f05  mov     edx, 73h ; 's'
0x140011f0a  call    WPP_SF_
0x140011f0f  mov     rcx, [rsi+40h]
0x140011f13  xor     edx, edx
0x140011f15  mov     rax, [rdi+0B8h]
0x140011f1c  lea     r9, [rcx+4AAh]
0x140011f23  mov     rax, [rax+8]
0x140011f27  mov     [r9], rdx
0x140011f2a  mov     [r9+8], edx
0x140011f2e  mov     byte ptr [r9], 3
0x140011f32  test    rbx, rbx
0x140011f35  jnz     short loc_140011F3C
0x140011f37  mov     al, [rax+0Bh]
0x140011f3a  jmp     short loc_140011F3E
0x140011f3c  mov     al, 12h
0x140011f3e  mov     [rcx+4AEh], al
0x140011f44  mov     r8d, 0Ch
0x140011f4a  lea     rax, USBSTOR_RequestSenseCdbCompletion
0x140011f51  mov     [rsp+58h+var_30], rbx; __int64
0x140011f56  mov     rdx, rdi; Irp
0x140011f59  mov     [rsp+58h+var_38], rax; __int64
0x140011f5e  mov     rcx, rsi; Object
0x140011f61  call    USBSTOR_IssueControlRequest
0x140011f66  mov     ebx, eax
0x140011f68  mov     rcx, cs:WPP_GLOBAL_Control
0x140011f6f  cmp     rcx, rbp
0x140011f72  jz      short loc_140011F9A
0x140011f74  mov     edx, [rcx+2Ch]
0x140011f77  test    dl, 1
0x140011f7a  jz      short loc_140011F9A
0x140011f7c  cmp     byte ptr [rcx+29h], 5
0x140011f80  jb      short loc_140011F9A
0x140011f82  mov     rcx, [rcx+18h]
0x140011f86  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140011f8d  mov     edx, 74h ; 't'
0x140011f92  mov     r9d, eax
0x140011f95  call    WPP_SF_d
0x140011f9a  mov     eax, ebx
0x140011f9c  add     rsp, 38h
0x140011fa0  pop     rdi
0x140011fa1  pop     rsi
0x140011fa2  pop     rbp
0x140011fa3  pop     rbx
0x140011fa4  retn
```
