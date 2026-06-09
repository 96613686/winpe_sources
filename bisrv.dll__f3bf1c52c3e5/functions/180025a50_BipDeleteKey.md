# BipDeleteKey

- ea: `0x180025a50`
- end: `0x180025d5f`
- name: `BipDeleteKey`
- size: `783`
- prototype: `__int64 __fastcall(void *, struct _UNICODE_STRING *)`
- caller_count: `5`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180023a78`
- `0x180024c30`
- `0x180025834`
- `0x180025a50`
- `0x180050420`

## callees

- `0x180025a50`
- `0x180026080`
- `0x1800310e4`
- `0x180049844`
- `0x18004df58`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180025ae6`
- `ntdll!NtOpenKey` at `0x180025ae6`
- `ntdll!RtlAppendUnicodeToString` at `0x180025c4f`
- `ntdll!RtlAppendUnicodeToString` at `0x180025c4f`
- `ntdll!NtEnumerateKey` at `0x180025b1e`
- `ntdll!NtEnumerateKey` at `0x180025b1e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180025c63`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180025c63`
- `ntdll!NtDeleteKey` at `0x180025b39`
- `ntdll!NtDeleteKey` at `0x180025b39`
- `ntdll!RtlFreeHeap` at `0x180025be4`
- `ntdll!RtlFreeHeap` at `0x180025d54`
- `ntdll!RtlFreeHeap` at `0x180025be4`
- `ntdll!RtlFreeHeap` at `0x180025d54`
- `ntdll!RtlAllocateHeap` at `0x180025bff`
- `ntdll!RtlAllocateHeap` at `0x180025bff`
- `ntdll!NtClose` at `0x180025b4e`
- `ntdll!NtClose` at `0x180025b4e`

## pseudocode

```c
__int64 __fastcall BipDeleteKey(void *a1, struct _UNICODE_STRING *a2)
{
  USHORT v4; // bp
  _DWORD *Heap; // rsi
  NTSTATUS appended; // eax
  NTSTATUS v7; // edi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  UNICODE_STRING Source; // [rsp+30h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-48h] BYREF
  ULONG Length; // [rsp+90h] [rbp+8h] BYREF
  void *KeyHandle; // [rsp+98h] [rbp+10h] BYREF

  KeyHandle = 0;
  Length = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Source = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids, a2->Buffer);
  v4 = a2->Length;
  KeyHandle = 0;
  Length = 0;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Heap = 0;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = a2;
  appended = NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
  v7 = appended;
  if ( appended < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 31;
LABEL_15:
      WPP_SF_d(v9[2], v10, WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids, (unsigned int)appended);
    }
  }
  else
  {
    while ( 1 )
    {
      while ( 1 )
      {
        appended = NtEnumerateKey(KeyHandle, 0, KeyBasicInformation, Heap, Length, &Length);
        v7 = appended;
        if ( appended == -2147483622 )
        {
          v7 = NtDeleteKey(KeyHandle);
          goto LABEL_7;
        }
        if ( appended != -1073741789 )
          break;
        if ( Heap )
          RtlFreeHeap(BipHeap, 0, Heap);
        Heap = RtlAllocateHeap(BipHeap, 0, Length + 2LL);
        if ( !Heap )
        {
          v7 = -1073741801;
          goto LABEL_7;
        }
      }
      if ( appended < 0 )
        break;
      v7 = BipConstructUnicodeString(&Source, Heap + 4, Heap[3] >> 1);
      if ( v7 < 0 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids);
        goto LABEL_7;
      }
      a2->Length = v4;
      appended = RtlAppendUnicodeToString(a2, L"\\");
      v7 = appended;
      if ( appended < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = 34;
          goto LABEL_15;
        }
        goto LABEL_7;
      }
      appended = RtlAppendUnicodeStringToString(a2, &Source);
      v7 = appended;
      if ( appended < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = 35;
          goto LABEL_15;
        }
        goto LABEL_7;
      }
      appended = BipDeleteKey(a1, a2);
      v7 = appended;
      if ( appended < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = 36;
          goto LABEL_15;
        }
        goto LABEL_7;
      }
    }
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 32;
      goto LABEL_15;
    }
  }
LABEL_7:
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( Heap )
    RtlFreeHeap(BipHeap, 0, Heap);
  a2->Length = v4;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180025a50  mov     rax, rsp
0x180025a53  mov     [rax+18h], rbx
0x180025a57  mov     [rax+20h], rbp
0x180025a5b  push    rsi
0x180025a5c  push    rdi
0x180025a5d  push    r14
0x180025a5f  sub     rsp, 70h
0x180025a63  xorps   xmm0, xmm0
0x180025a66  xor     edi, edi
0x180025a68  mov     [rax+10h], rdi
0x180025a6c  mov     rbx, rdx
0x180025a6f  mov     [rax+8], edi
0x180025a72  mov     r14, rcx
0x180025a75  movups  xmmword ptr [rax-48h], xmm0
0x180025a79  movups  xmmword ptr [rax-38h], xmm0
0x180025a7d  movups  xmmword ptr [rax-28h], xmm0
0x180025a81  movups  xmmword ptr [rax-58h], xmm0
0x180025a85  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a8c  test    byte ptr [rcx+1Ch], 8
0x180025a90  jz      short loc_180025A9C
0x180025a92  cmp     byte ptr [rcx+19h], 4
0x180025a96  jnb     loc_180025B91
0x180025a9c  movzx   ebp, word ptr [rbx]
0x180025a9f  lea     r8, [rsp+88h+ObjectAttributes]; ObjectAttributes
0x180025aa4  xorps   xmm0, xmm0
0x180025aa7  mov     [rsp+88h+KeyHandle], rdi
0x180025aaf  mov     edx, 0F003Fh; DesiredAccess
0x180025ab4  mov     [rsp+88h+arg_0], edi
0x180025abb  lea     rcx, [rsp+88h+KeyHandle]; KeyHandle
0x180025ac3  mov     [rsp+88h+ObjectAttributes.Length], 30h ; '0'
0x180025acb  movdqu  xmmword ptr [rsp+88h+ObjectAttributes.SecurityDescriptor], xmm0
0x180025ad1  mov     rsi, rdi
0x180025ad4  mov     [rsp+88h+ObjectAttributes.RootDirectory], r14
0x180025ad9  mov     [rsp+88h+ObjectAttributes.Attributes], 40h ; '@'
0x180025ae1  mov     [rsp+88h+ObjectAttributes.ObjectName], rbx
0x180025ae6  call    cs:__imp_NtOpenKey
0x180025aec  mov     edi, eax
0x180025aee  test    eax, eax
0x180025af0  js      loc_180025B77
0x180025af6  mov     rcx, [rsp+88h+KeyHandle]; KeyHandle
0x180025afe  lea     rax, [rsp+88h+arg_0]
0x180025b06  mov     [rsp+88h+ResultLength], rax; ResultLength
0x180025b0b  mov     r9, rsi; KeyInformation
0x180025b0e  mov     eax, [rsp+88h+arg_0]
0x180025b15  xor     r8d, r8d; KeyInformationClass
0x180025b18  xor     edx, edx; Index
0x180025b1a  mov     [rsp+88h+Length], eax; Length
0x180025b1e  call    cs:__imp_NtEnumerateKey
0x180025b24  mov     edi, eax
0x180025b26  cmp     eax, 8000001Ah
0x180025b2b  jnz     loc_180025BCC
0x180025b31  mov     rcx, [rsp+88h+KeyHandle]; KeyHandle
0x180025b39  call    cs:__imp_NtDeleteKey
0x180025b3f  mov     edi, eax
0x180025b41  mov     rcx, [rsp+88h+KeyHandle]; Handle
0x180025b49  test    rcx, rcx
0x180025b4c  jz      short loc_180025B54
0x180025b4e  call    cs:__imp_NtClose
0x180025b54  test    rsi, rsi
0x180025b57  jnz     loc_180025D48
0x180025b5d  lea     r11, [rsp+88h+var_18]
0x180025b62  mov     [rbx], bp
0x180025b65  mov     rbx, [r11+30h]
0x180025b69  mov     eax, edi
0x180025b6b  mov     rbp, [r11+38h]
0x180025b6f  mov     rsp, r11
0x180025b72  pop     r14
0x180025b74  pop     rdi
0x180025b75  pop     rsi
0x180025b76  retn
0x180025b77  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b7e  test    byte ptr [rcx+1Ch], 8
0x180025b82  jz      short loc_180025B41
0x180025b84  cmp     byte ptr [rcx+19h], 2
0x180025b88  jb      short loc_180025B41
0x180025b8a  mov     edx, 1Fh
0x180025b8f  jmp     short loc_180025BB4
0x180025b91  mov     r9, [rbx+8]
0x180025b95  lea     r8, WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids
0x180025b9c  mov     rcx, [rcx+10h]
0x180025ba0  mov     edx, 1Eh
0x180025ba5  call    WPP_SF_S
0x180025baa  jmp     loc_180025A9C
0x180025baf  mov     edx, 23h ; '#'
0x180025bb4  mov     rcx, [rcx+10h]
0x180025bb8  lea     r8, WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids
0x180025bbf  mov     r9d, eax
0x180025bc2  call    WPP_SF_d
0x180025bc7  jmp     loc_180025B41
0x180025bcc  cmp     eax, 0C0000023h
0x180025bd1  jnz     short loc_180025C1B
0x180025bd3  test    rsi, rsi
0x180025bd6  jz      short loc_180025BEA
0x180025bd8  mov     rcx, cs:BipHeap; HeapHandle
0x180025bdf  mov     r8, rsi; P
0x180025be2  xor     edx, edx; Flags
0x180025be4  call    cs:__imp_RtlFreeHeap
0x180025bea  mov     r8d, [rsp+88h+arg_0]
0x180025bf2  xor     edx, edx; Flags
0x180025bf4  mov     rcx, cs:BipHeap; HeapHandle
0x180025bfb  add     r8, 2; Size
0x180025bff  call    cs:__imp_RtlAllocateHeap
0x180025c05  mov     rsi, rax
0x180025c08  test    rax, rax
0x180025c0b  jnz     loc_180025AF6
0x180025c11  mov     edi, 0C0000017h
0x180025c16  jmp     loc_180025B41
0x180025c1b  test    eax, eax
0x180025c1d  js      loc_180025D23
0x180025c23  mov     r8d, [rsi+0Ch]
0x180025c27  lea     rdx, [rsi+10h]
0x180025c2b  shr     r8d, 1
0x180025c2e  lea     rcx, [rsp+88h+Source]
0x180025c33  call    BipConstructUnicodeString
0x180025c38  mov     edi, eax
0x180025c3a  test    eax, eax
0x180025c3c  js      loc_180025CEE
0x180025c42  lea     rdx, asc_1800A13D0; "\\"
0x180025c49  mov     [rbx], bp
0x180025c4c  mov     rcx, rbx; Destination
0x180025c4f  call    cs:__imp_RtlAppendUnicodeToString
0x180025c55  mov     edi, eax
0x180025c57  test    eax, eax
0x180025c59  js      short loc_180025CC9
0x180025c5b  lea     rdx, [rsp+88h+Source]; Source
0x180025c60  mov     rcx, rbx; Destination
0x180025c63  call    cs:__imp_RtlAppendUnicodeStringToString
0x180025c69  mov     edi, eax
0x180025c6b  test    eax, eax
0x180025c6d  js      short loc_180025CA9
0x180025c6f  mov     rdx, rbx
0x180025c72  mov     rcx, r14
0x180025c75  call    BipDeleteKey
0x180025c7a  mov     edi, eax
0x180025c7c  test    eax, eax
0x180025c7e  jns     loc_180025AF6
0x180025c84  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c8b  test    byte ptr [rcx+1Ch], 8
0x180025c8f  jz      loc_180025B41
0x180025c95  cmp     byte ptr [rcx+19h], 2
0x180025c99  jb      loc_180025B41
0x180025c9f  mov     edx, 24h ; '$'
0x180025ca4  jmp     loc_180025BB4
0x180025ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cb0  test    byte ptr [rcx+1Ch], 8
0x180025cb4  jz      loc_180025B41
0x180025cba  cmp     byte ptr [rcx+19h], 2
0x180025cbe  jb      loc_180025B41
0x180025cc4  jmp     loc_180025BAF
0x180025cc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cd0  test    byte ptr [rcx+1Ch], 8
0x180025cd4  jz      loc_180025B41
0x180025cda  cmp     byte ptr [rcx+19h], 2
0x180025cde  jb      loc_180025B41
0x180025ce4  mov     edx, 22h ; '"'
0x180025ce9  jmp     loc_180025BB4
0x180025cee  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cf5  test    byte ptr [rcx+1Ch], 8
0x180025cf9  jz      loc_180025B41
0x180025cff  cmp     byte ptr [rcx+19h], 2
0x180025d03  jb      loc_180025B41
0x180025d09  mov     rcx, [rcx+10h]
0x180025d0d  lea     r8, WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids
0x180025d14  mov     edx, 21h ; '!'
0x180025d19  call    WPP_SF_
0x180025d1e  jmp     loc_180025B41
0x180025d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d2a  test    byte ptr [rcx+1Ch], 8
0x180025d2e  jz      loc_180025B41
0x180025d34  cmp     byte ptr [rcx+19h], 2
0x180025d38  jb      loc_180025B41
0x180025d3e  mov     edx, 20h ; ' '
0x180025d43  jmp     loc_180025BB4
0x180025d48  mov     rcx, cs:BipHeap; HeapHandle
0x180025d4f  mov     r8, rsi; P
0x180025d52  xor     edx, edx; Flags
0x180025d54  call    cs:__imp_RtlFreeHeap
0x180025d5a  jmp     loc_180025B5D
```
