# USBSTOR_PdoQueryDeviceText

- ea: `0x140028b50`
- end: `0x140028d24`
- name: `USBSTOR_PdoQueryDeviceText`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140023f70`

## callees

- `0x140003630`
- `0x14000e40c`
- `0x1400105e8`
- `0x140010664`
- `0x140013950`
- `0x140013d40`
- `0x140028b50`

## import_xrefs

- `ntoskrnl!RtlInitAnsiString` at `0x140028c70`
- `ntoskrnl!RtlInitAnsiString` at `0x140028c70`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140028c89`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140028c89`
- `ntoskrnl!IofCompleteRequest` at `0x140028cb2`
- `ntoskrnl!IofCompleteRequest` at `0x140028cb2`

## pseudocode

```c
__int64 __fastcall USBSTOR_PdoQueryDeviceText(__int64 a1, IRP *a2)
{
  __int64 v4; // rbx
  char *v5; // rcx
  int i; // edx
  int v7; // edx
  NTSTATUS v8; // eax
  PWSTR Buffer; // rcx
  NTSTATUS Status; // ebx
  struct _STRING DestinationString; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING v13; // [rsp+30h] [rbp-D0h] BYREF
  char SourceString[256]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+140h] [rbp+40h] BYREF

  DestinationString = 0;
  v13 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 138, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1413763408, a1, a2, 0);
  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length )
  {
    Status = a2->IoStatus.Status;
  }
  else
  {
    v4 = *(_QWORD *)(a1 + 64);
    memset(SourceString, 0, sizeof(SourceString));
    v5 = SourceString;
    *(_QWORD *)SourceString = *(_QWORD *)(v4 + 80);
    for ( i = 7; i >= 0; --i )
    {
      if ( (SourceString[i] & 0xDF) != 0 )
      {
        SourceString[i + 1] = 32;
        v5 = &SourceString[i + 2];
        break;
      }
    }
    v7 = 15;
    *(_OWORD *)v5 = *(_OWORD *)(v4 + 88);
    while ( v7 >= 0 )
    {
      if ( (v5[v7] & 0xDF) != 0 )
      {
        v5[v7 + 1] = 32;
        v5 += v7 + 2;
        break;
      }
      --v7;
    }
    RtlStringCbPrintfA(v5, (char *)&v15 - v5, "USB Device");
    RtlInitAnsiString(&DestinationString, SourceString);
    v8 = RtlAnsiStringToUnicodeString(&v13, &DestinationString, 1u);
    Buffer = 0;
    Status = v8;
    if ( v8 >= 0 )
      Buffer = v13.Buffer;
    a2->IoStatus.Information = (ULONG_PTR)Buffer;
  }
  a2->IoStatus.Status = Status;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 139, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1952739696, Status, 0, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140028b50  mov     [rsp-8+arg_10], rbx
0x140028b55  push    rbp
0x140028b56  push    rsi
0x140028b57  push    rdi
0x140028b58  lea     rbp, [rsp-50h]
0x140028b5d  sub     rsp, 150h
0x140028b64  mov     rax, cs:__security_cookie
0x140028b6b  xor     rax, rsp
0x140028b6e  mov     [rbp+60h+var_20], rax
0x140028b72  xorps   xmm0, xmm0
0x140028b75  xorps   xmm1, xmm1
0x140028b78  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x140028b7d  mov     rdi, rdx
0x140028b80  mov     rbx, rcx
0x140028b83  movups  xmmword ptr [rsp+160h+var_130.Length], xmm1
0x140028b88  mov     rcx, cs:WPP_GLOBAL_Control
0x140028b8f  lea     rsi, WPP_GLOBAL_Control
0x140028b96  cmp     rcx, rsi
0x140028b99  jz      short loc_140028BBD
0x140028b9b  mov     eax, [rcx+2Ch]
0x140028b9e  test    al, 2
0x140028ba0  jz      short loc_140028BBD
0x140028ba2  cmp     byte ptr [rcx+29h], 4
0x140028ba6  jb      short loc_140028BBD
0x140028ba8  mov     rcx, [rcx+18h]
0x140028bac  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140028bb3  mov     edx, 8Ah
0x140028bb8  call    WPP_SF_
0x140028bbd  xor     r9d, r9d
0x140028bc0  mov     r8, rdi
0x140028bc3  mov     rdx, rbx
0x140028bc6  mov     ecx, 54445150h
0x140028bcb  call    USBSTOR_LogEntry
0x140028bd0  mov     rax, [rdi+0B8h]
0x140028bd7  cmp     dword ptr [rax+8], 0
0x140028bdb  jnz     loc_140028CA7
0x140028be1  mov     rbx, [rbx+40h]
0x140028be5  lea     rcx, [rsp+160h+SourceString]; void *
0x140028bea  xor     edx, edx; Val
0x140028bec  mov     r8d, 100h; Size
0x140028bf2  call    memset
0x140028bf7  mov     rax, [rbx+50h]
0x140028bfb  lea     rcx, [rsp+160h+SourceString]
0x140028c00  mov     qword ptr [rsp+160h+SourceString], rax
0x140028c05  mov     edx, 7
0x140028c0a  test    edx, edx
0x140028c0c  js      short loc_140028C28
0x140028c0e  movsxd  r8, edx
0x140028c11  test    [rsp+r8+160h+SourceString], 0DFh
0x140028c17  jnz     short loc_140028C1D
0x140028c19  dec     edx
0x140028c1b  jmp     short loc_140028C0A
0x140028c1d  mov     [rsp+r8+160h+SourceString+1], 20h ; ' '
0x140028c23  lea     rcx, [rsp+r8+160h+SourceString+2]
0x140028c28  movups  xmm0, xmmword ptr [rbx+58h]
0x140028c2c  mov     edx, 0Fh
0x140028c31  movdqu  xmmword ptr [rcx], xmm0
0x140028c35  test    edx, edx
0x140028c37  js      short loc_140028C53
0x140028c39  movsxd  r8, edx
0x140028c3c  test    byte ptr [r8+rcx], 0DFh
0x140028c41  jnz     short loc_140028C47
0x140028c43  dec     edx
0x140028c45  jmp     short loc_140028C35
0x140028c47  lea     rax, [r8+rcx]
0x140028c4b  mov     byte ptr [rax+1], 20h ; ' '
0x140028c4f  lea     rcx, [rax+2]; pszDest
0x140028c53  lea     rdx, [rbp+60h+var_20]
0x140028c57  sub     rdx, rcx; cbDest
0x140028c5a  lea     r8, aUsbDevice; "USB Device"
0x140028c61  call    RtlStringCbPrintfA
0x140028c66  lea     rdx, [rsp+160h+SourceString]; SourceString
0x140028c6b  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x140028c70  call    cs:__imp_RtlInitAnsiString
0x140028c77  nop     dword ptr [rax+rax+00h]
0x140028c7c  mov     r8b, 1; AllocateDestinationString
0x140028c7f  lea     rdx, [rsp+160h+DestinationString]; SourceString
0x140028c84  lea     rcx, [rsp+160h+var_130]; DestinationString
0x140028c89  call    cs:__imp_RtlAnsiStringToUnicodeString
0x140028c90  nop     dword ptr [rax+rax+00h]
0x140028c95  xor     ecx, ecx
0x140028c97  mov     ebx, eax
0x140028c99  test    eax, eax
0x140028c9b  cmovns  rcx, [rsp+160h+var_130.Buffer]
0x140028ca1  mov     [rdi+38h], rcx
0x140028ca5  jmp     short loc_140028CAA
0x140028ca7  mov     ebx, [rdi+30h]
0x140028caa  xor     edx, edx; PriorityBoost
0x140028cac  mov     [rdi+30h], ebx
0x140028caf  mov     rcx, rdi; Irp
0x140028cb2  call    cs:__imp_IofCompleteRequest
0x140028cb9  nop     dword ptr [rax+rax+00h]
0x140028cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x140028cc5  cmp     rcx, rsi
0x140028cc8  jz      short loc_140028CEF
0x140028cca  mov     eax, [rcx+2Ch]
0x140028ccd  test    al, 2
0x140028ccf  jz      short loc_140028CEF
0x140028cd1  cmp     byte ptr [rcx+29h], 4
0x140028cd5  jb      short loc_140028CEF
0x140028cd7  mov     rcx, [rcx+18h]
0x140028cdb  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140028ce2  mov     edx, 8Bh
0x140028ce7  mov     r9d, ebx
0x140028cea  call    WPP_SF_d
0x140028cef  movsxd  rdx, ebx
0x140028cf2  xor     r9d, r9d
0x140028cf5  xor     r8d, r8d
0x140028cf8  mov     ecx, 74647170h
0x140028cfd  call    USBSTOR_LogEntry
0x140028d02  mov     eax, ebx
0x140028d04  mov     rcx, [rbp+60h+var_20]
0x140028d08  xor     rcx, rsp; StackCookie
0x140028d0b  call    __security_check_cookie
0x140028d10  mov     rbx, [rsp+160h+arg_10]
0x140028d18  add     rsp, 150h
0x140028d1f  pop     rdi
0x140028d20  pop     rsi
0x140028d21  pop     rbp
0x140028d22  retn
```
