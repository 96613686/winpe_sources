# FltGetInstanceInformation

- ea: `0x1800757b0`
- end: `0x180075cbd`
- name: `FltGetInstanceInformation`
- size: `1293`
- prototype: `NTSTATUS __stdcall(PFLT_INSTANCE Instance, INSTANCE_INFORMATION_CLASS InformationClass, PVOID Buffer, ULONG BufferSize, PULONG BytesReturned)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180050350`
- `0x180056538`
- `0x1800753c0`
- `0x1800850e0`

## callees

- `0x18001ac40`
- `0x1800757b0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x18007592c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075981`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800759d9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075a2d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075a8a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075adf`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075b37`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075b8b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075bde`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075c33`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075c81`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007592c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075981`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800759d9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075a2d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075a8a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075adf`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075b37`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075b8b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075bde`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075c33`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180075c81`

## pseudocode

```c
NTSTATUS __stdcall FltGetInstanceInformation(
        PFLT_INSTANCE Instance,
        INSTANCE_INFORMATION_CLASS InformationClass,
        PVOID Buffer,
        ULONG BufferSize,
        PULONG BytesReturned)
{
  NTSTATUS result; // eax
  _UNICODE_STRING *p_Name; // rbx
  ULONG v9; // r15d
  unsigned __int16 v10; // ax
  __int64 v11; // r13
  unsigned __int16 v12; // ax
  unsigned __int16 v13; // r13
  _UNICODE_STRING *v14; // rdx
  unsigned __int16 v15; // ax
  __int64 v16; // rbx
  _UNICODE_STRING *v17; // rdx
  unsigned __int16 v18; // ax
  __int64 v19; // r13
  unsigned __int16 v20; // ax
  unsigned __int16 v21; // r13
  _UNICODE_STRING *p_DeviceName; // rdx
  unsigned __int16 v23; // ax
  __int64 v24; // rbx
  _UNICODE_STRING *v25; // rdx
  unsigned __int16 Length; // ax
  __int64 v27; // r13
  UNICODE_STRING DestinationString; // [rsp+20h] [rbp-10h] BYREF

  *BytesReturned = 0;
  DestinationString = 0;
  if ( InformationClass )
  {
    switch ( InformationClass )
    {
      case InstancePartialInformation:
        p_Name = &Instance->Name;
        v9 = Instance->Altitude.Length + 12 + Instance->Name.Length;
        break;
      case InstanceFullInformation:
        p_Name = &Instance->Name;
        v9 = Instance->Altitude.Length
           + Instance->Filter->Name.Length
           + Instance->Volume->DeviceName.Length
           + Instance->Name.Length
           + 20;
        break;
      case InstanceAggregateStandardInformation:
        p_Name = &Instance->Name;
        v9 = Instance->Altitude.Length
           + Instance->Filter->Name.Length
           + Instance->Volume->DeviceName.Length
           + Instance->Name.Length
           + 40;
        break;
      default:
        return -1073741811;
    }
  }
  else
  {
    p_Name = &Instance->Name;
    v9 = Instance->Name.Length + 8;
  }
  if ( BufferSize >= v9 )
  {
    if ( InformationClass )
    {
      if ( InformationClass == InstancePartialInformation )
      {
        *(_DWORD *)Buffer = 0;
        if ( v9 - 12 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - 12;
        else
          DestinationString.MaximumLength = -1;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + 12);
        RtlCopyUnicodeString(&DestinationString, p_Name);
        Length = p_Name->Length;
        *((_WORD *)Buffer + 2) = p_Name->Length;
        v27 = (unsigned __int16)(Length + 12);
        DestinationString.Length = 0;
        *((_WORD *)Buffer + 3) = 12;
        if ( v9 - (unsigned int)v27 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - v27;
        else
          DestinationString.MaximumLength = -1;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + v27);
        RtlCopyUnicodeString(&DestinationString, &Instance->Altitude);
        *((_WORD *)Buffer + 4) = Instance->Altitude.Length;
        result = 0;
        *((_WORD *)Buffer + 5) = v27;
      }
      else if ( InformationClass == InstanceFullInformation )
      {
        *(_DWORD *)Buffer = 0;
        if ( v9 - 20 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - 20;
        else
          DestinationString.MaximumLength = -1;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + 20);
        RtlCopyUnicodeString(&DestinationString, p_Name);
        v18 = p_Name->Length;
        *((_WORD *)Buffer + 2) = p_Name->Length;
        v19 = (unsigned __int16)(v18 + 20);
        DestinationString.Length = 0;
        *((_WORD *)Buffer + 3) = 20;
        if ( v9 - (unsigned int)v19 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - v19;
        else
          DestinationString.MaximumLength = -1;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + v19);
        RtlCopyUnicodeString(&DestinationString, &Instance->Altitude);
        v20 = Instance->Altitude.Length;
        *((_WORD *)Buffer + 4) = v20;
        *((_WORD *)Buffer + 5) = v19;
        v21 = v20 + v19;
        DestinationString.Length = 0;
        if ( v9 - v21 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - v21;
        else
          DestinationString.MaximumLength = -1;
        p_DeviceName = &Instance->Volume->DeviceName;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + v21);
        RtlCopyUnicodeString(&DestinationString, p_DeviceName);
        v23 = DestinationString.Length;
        *((_WORD *)Buffer + 6) = DestinationString.Length;
        *((_WORD *)Buffer + 7) = v21;
        v24 = (unsigned __int16)(v23 + v21);
        DestinationString.Length = 0;
        if ( v9 - (unsigned __int16)v24 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - v24;
        else
          DestinationString.MaximumLength = -1;
        v25 = &Instance->Filter->Name;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + v24);
        RtlCopyUnicodeString(&DestinationString, v25);
        result = 0;
        *((_WORD *)Buffer + 8) = Instance->Filter->Name.Length;
        *((_WORD *)Buffer + 9) = v24;
      }
      else
      {
        *(_DWORD *)Buffer = 0;
        *((_DWORD *)Buffer + 1) = 1;
        *((_DWORD *)Buffer + 3) = Instance->Volume->Frame->FrameID;
        *((_DWORD *)Buffer + 4) = Instance->Volume->FileSystemType;
        *((_DWORD *)Buffer + 2) = 0;
        if ( (unsigned __int8)FltpIsVolumeDetached(Instance->Volume) )
          *((_DWORD *)Buffer + 2) |= 1u;
        DestinationString.Length = 0;
        if ( v9 - 40 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - 40;
        else
          DestinationString.MaximumLength = -1;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + 40);
        RtlCopyUnicodeString(&DestinationString, p_Name);
        v10 = p_Name->Length;
        *((_WORD *)Buffer + 10) = p_Name->Length;
        v11 = (unsigned __int16)(v10 + 40);
        DestinationString.Length = 0;
        *((_WORD *)Buffer + 11) = 40;
        if ( v9 - (unsigned int)v11 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - v11;
        else
          DestinationString.MaximumLength = -1;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + v11);
        RtlCopyUnicodeString(&DestinationString, &Instance->Altitude);
        v12 = Instance->Altitude.Length;
        *((_WORD *)Buffer + 12) = v12;
        *((_WORD *)Buffer + 13) = v11;
        v13 = v12 + v11;
        DestinationString.Length = 0;
        if ( v9 - v13 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - v13;
        else
          DestinationString.MaximumLength = -1;
        v14 = &Instance->Volume->DeviceName;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + v13);
        RtlCopyUnicodeString(&DestinationString, v14);
        v15 = DestinationString.Length;
        *((_WORD *)Buffer + 14) = DestinationString.Length;
        *((_WORD *)Buffer + 15) = v13;
        v16 = (unsigned __int16)(v15 + v13);
        DestinationString.Length = 0;
        if ( v9 - (unsigned __int16)v16 <= 0xFFFF )
          DestinationString.MaximumLength = v9 - v16;
        else
          DestinationString.MaximumLength = -1;
        v17 = &Instance->Filter->Name;
        DestinationString.Buffer = (wchar_t *)((char *)Buffer + v16);
        RtlCopyUnicodeString(&DestinationString, v17);
        *((_WORD *)Buffer + 16) = Instance->Filter->Name.Length;
        *((_WORD *)Buffer + 17) = v16;
        *((_DWORD *)Buffer + 9) = Instance->SupportedFeatures;
        result = 0;
      }
    }
    else
    {
      *(_DWORD *)Buffer = 0;
      if ( v9 - 8 <= 0xFFFF )
        DestinationString.MaximumLength = v9 - 8;
      else
        DestinationString.MaximumLength = -1;
      DestinationString.Buffer = (wchar_t *)((char *)Buffer + 8);
      RtlCopyUnicodeString(&DestinationString, p_Name);
      *((_WORD *)Buffer + 2) = p_Name->Length;
      result = 0;
      *((_WORD *)Buffer + 3) = 8;
    }
    *BytesReturned = v9;
  }
  else
  {
    *BytesReturned = v9;
    return -1073741789;
  }
  return result;
}

```

## disassembly

```asm
0x1800757b0  mov     [rsp-28h+arg_8], rbx
0x1800757b5  mov     [rsp-28h+arg_10], rsi
0x1800757ba  push    rbp
0x1800757bb  push    rdi
0x1800757bc  push    r13
0x1800757be  push    r14
0x1800757c0  push    r15
0x1800757c2  mov     rbp, rsp
0x1800757c5  sub     rsp, 30h
0x1800757c9  mov     rdi, [rbp+BytesReturned]
0x1800757cd  xor     r13d, r13d
0x1800757d0  xorps   xmm0, xmm0
0x1800757d3  mov     rsi, r8
0x1800757d6  mov     r10d, edx
0x1800757d9  mov     r14, rcx
0x1800757dc  mov     eax, edx
0x1800757de  mov     [rdi], r13d
0x1800757e1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800757e5  test    edx, edx
0x1800757e7  jz      loc_18007586F
0x1800757ed  sub     eax, 1
0x1800757f0  jz      short loc_18007585A
0x1800757f2  sub     eax, 1
0x1800757f5  jz      short loc_180075830
0x1800757f7  cmp     eax, 1
0x1800757fa  jz      short loc_180075806
0x1800757fc  mov     eax, 0C000000Dh
0x180075801  jmp     loc_180075CA5
0x180075806  mov     rax, [rcx+40h]
0x18007580a  lea     rbx, [rcx+68h]
0x18007580e  movzx   r15d, word ptr [rbx]
0x180075812  add     r15d, 28h ; '('
0x180075816  movzx   edx, word ptr [rax+70h]
0x18007581a  mov     rax, [rcx+48h]
0x18007581e  movzx   ecx, word ptr [rax+40h]
0x180075822  movzx   eax, word ptr [r14+58h]
0x180075827  add     edx, ecx
0x180075829  add     edx, eax
0x18007582b  add     r15d, edx
0x18007582e  jmp     short loc_18007587C
0x180075830  mov     rax, [rcx+40h]
0x180075834  lea     rbx, [rcx+68h]
0x180075838  movzx   r15d, word ptr [rbx]
0x18007583c  add     r15d, 14h
0x180075840  movzx   edx, word ptr [rax+70h]
0x180075844  mov     rax, [rcx+48h]
0x180075848  movzx   ecx, word ptr [rax+40h]
0x18007584c  movzx   eax, word ptr [r14+58h]
0x180075851  add     edx, ecx
0x180075853  add     edx, eax
0x180075855  add     r15d, edx
0x180075858  jmp     short loc_18007587C
0x18007585a  movzx   r15d, word ptr [rcx+68h]
0x18007585f  lea     rbx, [rcx+68h]
0x180075863  movzx   ecx, word ptr [rcx+58h]
0x180075867  add     ecx, 0Ch
0x18007586a  add     r15d, ecx
0x18007586d  jmp     short loc_18007587C
0x18007586f  movzx   r15d, word ptr [rcx+68h]
0x180075874  lea     rbx, [rcx+68h]
0x180075878  add     r15d, 8
0x18007587c  cmp     r9d, r15d
0x18007587f  jnb     short loc_18007588E
0x180075881  mov     [rdi], r15d
0x180075884  mov     eax, 0C0000023h
0x180075889  jmp     loc_180075CA5
0x18007588e  mov     [rsp+30h+arg_0], r12
0x180075893  test    r10d, r10d
0x180075896  jz      loc_180075C51
0x18007589c  sub     r10d, 1
0x1800758a0  jz      loc_180075BAE
0x1800758a6  sub     r10d, 1
0x1800758aa  jz      loc_180075A5A
0x1800758b0  cmp     r10d, 1
0x1800758b4  jz      short loc_1800758C0
0x1800758b6  mov     eax, 0C000000Dh
0x1800758bb  jmp     loc_180075CA0
0x1800758c0  mov     [r8], r13d
0x1800758c3  mov     dword ptr [r8+4], 1
0x1800758cb  mov     rax, [r14+40h]
0x1800758cf  mov     rcx, [rax+68h]
0x1800758d3  mov     eax, [rcx+18h]
0x1800758d6  mov     [r8+0Ch], eax
0x1800758da  mov     rax, [r14+40h]
0x1800758de  mov     ecx, [rax+3Ch]
0x1800758e1  mov     [r8+10h], ecx
0x1800758e5  mov     [r8+8], r13d
0x1800758e9  mov     rcx, [r14+40h]
0x1800758ed  call    FltpIsVolumeDetached
0x1800758f2  test    al, al
0x1800758f4  jz      short loc_1800758FA
0x1800758f6  or      dword ptr [rsi+8], 1
0x1800758fa  lea     eax, [r15-28h]
0x1800758fe  mov     [rbp+DestinationString.Length], r13w
0x180075903  mov     r12d, 0FFFFh
0x180075909  cmp     eax, r12d
0x18007590c  jbe     short loc_180075915
0x18007590e  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075913  jmp     short loc_18007591D
0x180075915  lea     eax, [r15-28h]
0x180075919  mov     [rbp+DestinationString.MaximumLength], ax
0x18007591d  lea     rax, [rsi+28h]
0x180075921  mov     rdx, rbx; SourceString
0x180075924  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075928  mov     [rbp+DestinationString.Buffer], rax
0x18007592c  call    cs:__imp_RtlCopyUnicodeString
0x180075933  nop     dword ptr [rax+rax+00h]
0x180075938  movzx   eax, word ptr [rbx]
0x18007593b  mov     [rsi+14h], ax
0x18007593f  add     ax, 28h ; '('
0x180075943  movzx   r13d, ax
0x180075947  xor     eax, eax
0x180075949  mov     [rbp+DestinationString.Length], ax
0x18007594d  mov     eax, r15d
0x180075950  sub     eax, r13d
0x180075953  mov     word ptr [rsi+16h], 28h ; '('
0x180075959  cmp     eax, r12d
0x18007595c  jbe     short loc_180075965
0x18007595e  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075963  jmp     short loc_180075971
0x180075965  movzx   eax, r15w
0x180075969  sub     ax, r13w
0x18007596d  mov     [rbp+DestinationString.MaximumLength], ax
0x180075971  lea     rax, [rsi+r13]
0x180075975  lea     rdx, [r14+58h]; SourceString
0x180075979  mov     [rbp+DestinationString.Buffer], rax
0x18007597d  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075981  call    cs:__imp_RtlCopyUnicodeString
0x180075988  nop     dword ptr [rax+rax+00h]
0x18007598d  movzx   eax, word ptr [r14+58h]
0x180075992  mov     [rsi+18h], ax
0x180075996  mov     [rsi+1Ah], r13w
0x18007599b  add     r13w, ax
0x18007599f  xor     eax, eax
0x1800759a1  movzx   ebx, r13w
0x1800759a5  mov     [rbp+DestinationString.Length], ax
0x1800759a9  mov     eax, r15d
0x1800759ac  sub     eax, ebx
0x1800759ae  cmp     eax, r12d
0x1800759b1  jbe     short loc_1800759BA
0x1800759b3  mov     [rbp+DestinationString.MaximumLength], r12w
0x1800759b8  jmp     short loc_1800759C5
0x1800759ba  movzx   eax, r15w
0x1800759be  sub     ax, bx
0x1800759c1  mov     [rbp+DestinationString.MaximumLength], ax
0x1800759c5  mov     rdx, [r14+40h]
0x1800759c9  lea     rax, [rsi+rbx]
0x1800759cd  add     rdx, 70h ; 'p'; SourceString
0x1800759d1  mov     [rbp+DestinationString.Buffer], rax
0x1800759d5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800759d9  call    cs:__imp_RtlCopyUnicodeString
0x1800759e0  nop     dword ptr [rax+rax+00h]
0x1800759e5  movzx   eax, [rbp+DestinationString.Length]
0x1800759e9  mov     [rsi+1Ch], ax
0x1800759ed  mov     [rsi+1Eh], bx
0x1800759f1  add     bx, ax
0x1800759f4  xor     eax, eax
0x1800759f6  movzx   ebx, bx
0x1800759f9  mov     [rbp+DestinationString.Length], ax
0x1800759fd  mov     eax, r15d
0x180075a00  sub     eax, ebx
0x180075a02  cmp     eax, r12d
0x180075a05  jbe     short loc_180075A0E
0x180075a07  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075a0c  jmp     short loc_180075A19
0x180075a0e  movzx   eax, r15w
0x180075a12  sub     ax, bx
0x180075a15  mov     [rbp+DestinationString.MaximumLength], ax
0x180075a19  mov     rdx, [r14+48h]
0x180075a1d  lea     rax, [rsi+rbx]
0x180075a21  add     rdx, 40h ; '@'; SourceString
0x180075a25  mov     [rbp+DestinationString.Buffer], rax
0x180075a29  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075a2d  call    cs:__imp_RtlCopyUnicodeString
0x180075a34  nop     dword ptr [rax+rax+00h]
0x180075a39  mov     rax, [r14+48h]
0x180075a3d  movzx   ecx, word ptr [rax+40h]
0x180075a41  mov     [rsi+20h], cx
0x180075a45  mov     [rsi+22h], bx
0x180075a49  mov     eax, [r14+2C0h]
0x180075a50  mov     [rsi+24h], eax
0x180075a53  xor     eax, eax
0x180075a55  jmp     loc_180075C9D
0x180075a5a  lea     eax, [r15-14h]
0x180075a5e  mov     [r8], r13d
0x180075a61  mov     r12d, 0FFFFh
0x180075a67  cmp     eax, r12d
0x180075a6a  jbe     short loc_180075A73
0x180075a6c  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075a71  jmp     short loc_180075A7B
0x180075a73  lea     eax, [r15-14h]
0x180075a77  mov     [rbp+DestinationString.MaximumLength], ax
0x180075a7b  lea     rax, [r8+14h]
0x180075a7f  mov     rdx, rbx; SourceString
0x180075a82  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075a86  mov     [rbp+DestinationString.Buffer], rax
0x180075a8a  call    cs:__imp_RtlCopyUnicodeString
0x180075a91  nop     dword ptr [rax+rax+00h]
0x180075a96  movzx   eax, word ptr [rbx]
0x180075a99  mov     [rsi+4], ax
0x180075a9d  add     ax, 14h
0x180075aa1  movzx   r13d, ax
0x180075aa5  xor     eax, eax
0x180075aa7  mov     [rbp+DestinationString.Length], ax
0x180075aab  mov     eax, r15d
0x180075aae  sub     eax, r13d
0x180075ab1  mov     word ptr [rsi+6], 14h
0x180075ab7  cmp     eax, r12d
0x180075aba  jbe     short loc_180075AC3
0x180075abc  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075ac1  jmp     short loc_180075ACF
0x180075ac3  movzx   eax, r15w
0x180075ac7  sub     ax, r13w
0x180075acb  mov     [rbp+DestinationString.MaximumLength], ax
0x180075acf  lea     rax, [rsi+r13]
0x180075ad3  lea     rdx, [r14+58h]; SourceString
0x180075ad7  mov     [rbp+DestinationString.Buffer], rax
0x180075adb  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075adf  call    cs:__imp_RtlCopyUnicodeString
0x180075ae6  nop     dword ptr [rax+rax+00h]
0x180075aeb  movzx   eax, word ptr [r14+58h]
0x180075af0  mov     [rsi+8], ax
0x180075af4  mov     [rsi+0Ah], r13w
0x180075af9  add     r13w, ax
0x180075afd  xor     eax, eax
0x180075aff  movzx   ebx, r13w
0x180075b03  mov     [rbp+DestinationString.Length], ax
0x180075b07  mov     eax, r15d
0x180075b0a  sub     eax, ebx
0x180075b0c  cmp     eax, r12d
0x180075b0f  jbe     short loc_180075B18
0x180075b11  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075b16  jmp     short loc_180075B23
0x180075b18  movzx   eax, r15w
0x180075b1c  sub     ax, bx
0x180075b1f  mov     [rbp+DestinationString.MaximumLength], ax
0x180075b23  mov     rdx, [r14+40h]
0x180075b27  lea     rax, [rsi+rbx]
0x180075b2b  add     rdx, 70h ; 'p'; SourceString
0x180075b2f  mov     [rbp+DestinationString.Buffer], rax
0x180075b33  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075b37  call    cs:__imp_RtlCopyUnicodeString
0x180075b3e  nop     dword ptr [rax+rax+00h]
0x180075b43  movzx   eax, [rbp+DestinationString.Length]
0x180075b47  mov     [rsi+0Ch], ax
0x180075b4b  mov     [rsi+0Eh], bx
0x180075b4f  add     bx, ax
0x180075b52  xor     eax, eax
0x180075b54  movzx   ebx, bx
0x180075b57  mov     [rbp+DestinationString.Length], ax
0x180075b5b  mov     eax, r15d
0x180075b5e  sub     eax, ebx
0x180075b60  cmp     eax, r12d
0x180075b63  jbe     short loc_180075B6C
0x180075b65  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075b6a  jmp     short loc_180075B77
0x180075b6c  movzx   eax, r15w
0x180075b70  sub     ax, bx
0x180075b73  mov     [rbp+DestinationString.MaximumLength], ax
0x180075b77  mov     rdx, [r14+48h]
0x180075b7b  lea     rax, [rsi+rbx]
0x180075b7f  add     rdx, 40h ; '@'; SourceString
0x180075b83  mov     [rbp+DestinationString.Buffer], rax
0x180075b87  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075b8b  call    cs:__imp_RtlCopyUnicodeString
0x180075b92  nop     dword ptr [rax+rax+00h]
0x180075b97  mov     rax, [r14+48h]
0x180075b9b  movzx   ecx, word ptr [rax+40h]
0x180075b9f  xor     eax, eax
0x180075ba1  mov     [rsi+10h], cx
0x180075ba5  mov     [rsi+12h], bx
0x180075ba9  jmp     loc_180075C9D
0x180075bae  lea     eax, [r15-0Ch]
0x180075bb2  mov     [r8], r13d
0x180075bb5  mov     r12d, 0FFFFh
0x180075bbb  cmp     eax, r12d
0x180075bbe  jbe     short loc_180075BC7
0x180075bc0  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075bc5  jmp     short loc_180075BCF
0x180075bc7  lea     eax, [r15-0Ch]
0x180075bcb  mov     [rbp+DestinationString.MaximumLength], ax
0x180075bcf  lea     rax, [r8+0Ch]
0x180075bd3  mov     rdx, rbx; SourceString
0x180075bd6  lea     rcx, [rbp+DestinationString]; DestinationString
0x180075bda  mov     [rbp+DestinationString.Buffer], rax
0x180075bde  call    cs:__imp_RtlCopyUnicodeString
0x180075be5  nop     dword ptr [rax+rax+00h]
0x180075bea  movzx   eax, word ptr [rbx]
0x180075bed  mov     [rsi+4], ax
0x180075bf1  add     ax, 0Ch
0x180075bf5  movzx   r13d, ax
0x180075bf9  xor     eax, eax
0x180075bfb  mov     [rbp+DestinationString.Length], ax
0x180075bff  mov     eax, r15d
0x180075c02  sub     eax, r13d
0x180075c05  mov     word ptr [rsi+6], 0Ch
0x180075c0b  cmp     eax, r12d
0x180075c0e  jbe     short loc_180075C17
0x180075c10  mov     [rbp+DestinationString.MaximumLength], r12w
0x180075c15  jmp     short loc_180075C23
  ... truncated ...
```
