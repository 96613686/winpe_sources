# USBSTOR_PdoQueryID

- ea: `0x140024870`
- end: `0x140024a1e`
- name: `USBSTOR_PdoQueryID`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140023f70`

## callees

- `0x140003630`
- `0x1400105e8`
- `0x140010664`
- `0x14001f1c4`
- `0x140023ab8`
- `0x140024870`
- `0x140024a24`
- `0x1400276a4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400248df`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400248df`
- `ntoskrnl!IofCompleteRequest` at `0x140024920`
- `ntoskrnl!IofCompleteRequest` at `0x140024920`

## pseudocode

```c
__int64 __fastcall USBSTOR_PdoQueryID(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  ULONG Length; // ecx
  ULONG v6; // ecx
  ULONG v7; // ecx
  int v8; // ebx
  int v10; // eax
  char v11; // dl
  PWSTR Buffer; // rax
  WCHAR v13; // cx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF

  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 128, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1145655632, a1, a2, 0);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  RtlInitUnicodeString(&DestinationString, 0);
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( !Length )
  {
    v10 = USBSTOR_PdoQueryDeviceId(a1, &DestinationString);
LABEL_21:
    v11 = 0;
    goto LABEL_22;
  }
  v6 = Length - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 != 1 )
      {
        v8 = -1073741637;
LABEL_10:
        a2->IoStatus.Information = 0;
        goto LABEL_11;
      }
      v10 = USBSTOR_PdoBusQueryInstanceId(a1, &DestinationString);
      goto LABEL_21;
    }
    v10 = USBSTOR_PdoQueryCompatibleIds(a1, &DestinationString);
  }
  else
  {
    v10 = USBSTOR_PdoQueryHardwareIds(a1, &DestinationString);
  }
  v11 = 1;
LABEL_22:
  v8 = v10;
  if ( v10 < 0 )
    goto LABEL_10;
  Buffer = DestinationString.Buffer;
  if ( !DestinationString.Buffer )
    goto LABEL_10;
  v13 = *DestinationString.Buffer;
  if ( *DestinationString.Buffer )
  {
    while ( 1 )
    {
      if ( v13 <= 0x20u || v13 > 0x7Fu || v13 == 44 )
        *Buffer = 95;
      v13 = *++Buffer;
      if ( !*Buffer )
      {
        if ( !v11 )
          break;
        v13 = *++Buffer;
        if ( !*Buffer )
          break;
      }
    }
    Buffer = DestinationString.Buffer;
  }
  a2->IoStatus.Information = (ULONG_PTR)Buffer;
LABEL_11:
  a2->IoStatus.Status = v8;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 129, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1684631920, v8, 0, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140024870  push    rbx
0x140024872  push    rbp
0x140024873  push    rsi
0x140024874  push    rdi
0x140024875  push    r14
0x140024877  sub     rsp, 30h
0x14002487b  xorps   xmm0, xmm0
0x14002487e  mov     rsi, rdx
0x140024881  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x140024886  mov     rdi, rcx
0x140024889  mov     rcx, cs:WPP_GLOBAL_Control
0x140024890  lea     r14, WPP_GLOBAL_Control
0x140024897  cmp     rcx, r14
0x14002489a  jz      short loc_1400248BE
0x14002489c  mov     eax, [rcx+2Ch]
0x14002489f  test    al, 2
0x1400248a1  jz      short loc_1400248BE
0x1400248a3  cmp     byte ptr [rcx+29h], 4
0x1400248a7  jb      short loc_1400248BE
0x1400248a9  mov     rcx, [rcx+18h]
0x1400248ad  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400248b4  mov     edx, 80h
0x1400248b9  call    WPP_SF_
0x1400248be  xor     r9d, r9d
0x1400248c1  mov     r8, rsi
0x1400248c4  mov     rdx, rdi
0x1400248c7  mov     ecx, 44495150h
0x1400248cc  call    USBSTOR_LogEntry
0x1400248d1  mov     rbx, [rsi+0B8h]
0x1400248d8  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1400248dd  xor     edx, edx; SourceString
0x1400248df  call    cs:__imp_RtlInitUnicodeString
0x1400248e6  nop     dword ptr [rax+rax+00h]
0x1400248eb  mov     ecx, [rbx+8]
0x1400248ee  xor     ebp, ebp
0x1400248f0  test    ecx, ecx
0x1400248f2  jz      loc_1400249AD
0x1400248f8  sub     ecx, 1
0x1400248fb  jz      loc_14002499E
0x140024901  sub     ecx, 1
0x140024904  jz      loc_14002498D
0x14002490a  cmp     ecx, 1
0x14002490d  jz      short loc_14002497E
0x14002490f  mov     ebx, 0C00000BBh
0x140024914  mov     [rsi+38h], rbp
0x140024918  xor     edx, edx; PriorityBoost
0x14002491a  mov     [rsi+30h], ebx
0x14002491d  mov     rcx, rsi; Irp
0x140024920  call    cs:__imp_IofCompleteRequest
0x140024927  nop     dword ptr [rax+rax+00h]
0x14002492c  mov     rcx, cs:WPP_GLOBAL_Control
0x140024933  cmp     rcx, r14
0x140024936  jz      short loc_14002495D
0x140024938  mov     eax, [rcx+2Ch]
0x14002493b  test    al, 2
0x14002493d  jz      short loc_14002495D
0x14002493f  cmp     byte ptr [rcx+29h], 4
0x140024943  jb      short loc_14002495D
0x140024945  mov     rcx, [rcx+18h]
0x140024949  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140024950  mov     edx, 81h
0x140024955  mov     r9d, ebx
0x140024958  call    WPP_SF_d
0x14002495d  movsxd  rdx, ebx
0x140024960  xor     r9d, r9d
0x140024963  xor     r8d, r8d
0x140024966  mov     ecx, 64697170h
0x14002496b  call    USBSTOR_LogEntry
0x140024970  mov     eax, ebx
0x140024972  add     rsp, 30h
0x140024976  pop     r14
0x140024978  pop     rdi
0x140024979  pop     rsi
0x14002497a  pop     rbp
0x14002497b  pop     rbx
0x14002497c  retn
0x14002497e  lea     rdx, [rsp+58h+DestinationString]
0x140024983  mov     rcx, rdi
0x140024986  call    USBSTOR_PdoBusQueryInstanceId
0x14002498b  jmp     short loc_1400249BA
0x14002498d  lea     rdx, [rsp+58h+DestinationString]
0x140024992  mov     rcx, rdi
0x140024995  call    USBSTOR_PdoQueryCompatibleIds
0x14002499a  mov     dl, 1
0x14002499c  jmp     short loc_1400249BD
0x14002499e  lea     rdx, [rsp+58h+DestinationString]
0x1400249a3  mov     rcx, rdi
0x1400249a6  call    USBSTOR_PdoQueryHardwareIds
0x1400249ab  jmp     short loc_14002499A
0x1400249ad  lea     rdx, [rsp+58h+DestinationString]
0x1400249b2  mov     rcx, rdi
0x1400249b5  call    USBSTOR_PdoQueryDeviceId
0x1400249ba  mov     dl, bpl
0x1400249bd  mov     ebx, eax
0x1400249bf  test    eax, eax
0x1400249c1  js      loc_140024914
0x1400249c7  mov     rax, [rsp+58h+DestinationString.Buffer]
0x1400249cc  test    rax, rax
0x1400249cf  jz      loc_140024914
0x1400249d5  movzx   ecx, word ptr [rax]
0x1400249d8  test    cx, cx
0x1400249db  jz      short loc_140024A15
0x1400249dd  cmp     cx, 20h ; ' '
0x1400249e1  jbe     short loc_1400249EF
0x1400249e3  cmp     cx, 7Fh
0x1400249e7  ja      short loc_1400249EF
0x1400249e9  cmp     cx, 2Ch ; ','
0x1400249ed  jnz     short loc_1400249F4
0x1400249ef  mov     word ptr [rax], 5Fh ; '_'
0x1400249f4  add     rax, 2
0x1400249f8  movzx   ecx, word ptr [rax]
0x1400249fb  test    cx, cx
0x1400249fe  jnz     short loc_1400249DD
0x140024a00  test    dl, dl
0x140024a02  jz      short loc_140024A10
0x140024a04  add     rax, 2
0x140024a08  movzx   ecx, word ptr [rax]
0x140024a0b  test    cx, cx
0x140024a0e  jnz     short loc_1400249DD
0x140024a10  mov     rax, [rsp+58h+DestinationString.Buffer]
0x140024a15  mov     [rsi+38h], rax
0x140024a19  jmp     loc_140024918
```
