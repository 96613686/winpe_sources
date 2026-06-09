# MbbUtilWwanToMbbSmsSetConfiguration(_WWAN_SET_SMS_CONFIGURATION *,ulong,_MBB_SET_SMS_CONFIGURATION * *,ulong *)

- ea: `0x1400235d8`
- end: `0x140023733`
- name: `?MbbUtilWwanToMbbSmsSetConfiguration@@YAJPEAU_WWAN_SET_SMS_CONFIGURATION@@KPEAPEAU_MBB_SET_SMS_CONFIGURATION@@PEAK@Z`
- size: `347`
- prototype: `__int64 __fastcall(struct _WWAN_SET_SMS_CONFIGURATION *, int, struct _MBB_SET_SMS_CONFIGURATION **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140017110`

## callees

- `0x1400051ac`
- `0x140020d40`
- `0x1400235d8`
- `0x140047e50`

## import_xrefs

- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140023649`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140023649`
- `ntoskrnl!ExAllocatePool2` at `0x1400236bb`
- `ntoskrnl!ExAllocatePool2` at `0x1400236bb`

## pseudocode

```c
__int64 __fastcall MbbUtilWwanToMbbSmsSetConfiguration(
        struct _WWAN_SET_SMS_CONFIGURATION *a1,
        int a2,
        struct _MBB_SET_SMS_CONFIGURATION **a3,
        unsigned int *a4)
{
  int v8; // edx
  unsigned int v9; // ebx
  __int64 result; // rax
  int v11; // esi
  unsigned int v12; // edi
  __int64 Pool2; // rbx
  int v14; // ecx
  int v15; // eax
  size_t Size; // [rsp+28h] [rbp-51h]
  struct _STRING SourceString; // [rsp+40h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int8 Src[48]; // [rsp+60h] [rbp-19h] BYREF

  *a3 = 0;
  SourceString.Buffer = (PCHAR)a1;
  SourceString.MaximumLength = 20;
  *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
  DestinationString.Buffer = (wchar_t *)Src;
  *(_QWORD *)&DestinationString.Length = 2752512;
  *a4 = 0;
  SourceString.Length = a2;
  v9 = RtlAnsiStringToUnicodeString(&DestinationString, &SourceString, 0);
  if ( v9 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        9,
        55,
        (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
        SourceString.Length,
        v9);
    }
    return v9;
  }
  else
  {
    v11 = 2 * a2;
    v12 = ((v11 + 3) & 0xFFFFFFFC) + 12;
    Pool2 = ExAllocatePool2(64, v12, 1683505741);
    if ( Pool2 )
    {
      v14 = *(_DWORD *)&a1[1].ScAddress[4];
      v15 = 0;
      if ( v14 )
      {
        LOBYTE(v15) = v14 != 4;
        ++v15;
      }
      *(_DWORD *)Pool2 = v15;
      LODWORD(Size) = v11;
      MbbUtilWriteStringToBuffer((unsigned __int8 *)Pool2, v12, 12, (struct _MBB_STRING *)(Pool2 + 4), Src, Size);
      *a3 = (struct _MBB_SET_SMS_CONFIGURATION *)Pool2;
      result = 0;
      *a4 = v12;
    }
    else
    {
      return 3221225626LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400235d8  push    rbp
0x1400235da  push    rbx
0x1400235db  push    rsi
0x1400235dc  push    rdi
0x1400235dd  push    r12
0x1400235df  push    r14
0x1400235e1  push    r15
0x1400235e3  lea     rbp, [rsp-27h]
0x1400235e8  sub     rsp, 0A0h
0x1400235ef  mov     rax, cs:__security_cookie
0x1400235f6  xor     rax, rsp
0x1400235f9  mov     [rbp+57h+var_40], rax
0x1400235fd  mov     esi, edx
0x1400235ff  mov     qword ptr [r8], 0
0x140023606  mov     eax, 14h
0x14002360b  mov     [rbp+57h+SourceString.Buffer], rcx
0x14002360f  mov     [rbp+57h+SourceString.MaximumLength], ax
0x140023613  lea     rdx, [rbp+57h+SourceString]; SourceString
0x140023617  lea     rax, [rbp+57h+var_70]
0x14002361b  mov     dword ptr [rbp+57h+SourceString+4], 0
0x140023622  mov     r15, r8
0x140023625  mov     [rbp+57h+DestinationString.Buffer], rax
0x140023629  mov     r14, rcx
0x14002362c  mov     qword ptr [rbp+57h+DestinationString.Length], 2A0000h
0x140023634  xor     r8d, r8d; AllocateDestinationString
0x140023637  mov     dword ptr [r9], 0
0x14002363e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140023642  mov     [rbp+57h+SourceString.Length], si
0x140023646  mov     r12, r9
0x140023649  call    cs:__imp_RtlAnsiStringToUnicodeString
0x140023650  nop     dword ptr [rax+rax+00h]
0x140023655  mov     ebx, eax
0x140023657  test    eax, eax
0x140023659  jz      short loc_1400236A3
0x14002365b  lea     rax, WPP_RECORDER_INITIALIZED
0x140023662  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023669  jz      short loc_14002369F
0x14002366b  movzx   ecx, [rbp+57h+SourceString.Length]
0x14002366f  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x140023676  mov     [rsp+0D0h+var_A0], ebx
0x14002367a  mov     r9d, 37h ; '7'
0x140023680  mov     dword ptr [rsp+0D0h+Size], ecx
0x140023684  mov     dl, 2
0x140023686  mov     rcx, cs:WPP_GLOBAL_Control
0x14002368d  mov     [rsp+0D0h+Src], rax
0x140023692  lea     r8d, [r9-2Eh]
0x140023696  mov     rcx, [rcx+40h]
0x14002369a  call    WPP_RECORDER_SF_DD
0x14002369f  mov     eax, ebx
0x1400236a1  jmp     short loc_140023714
0x1400236a3  add     esi, esi
0x1400236a5  mov     ecx, 40h ; '@'
0x1400236aa  mov     r8d, 6458424Dh
0x1400236b0  lea     edi, [rsi+3]
0x1400236b3  and     edi, 0FFFFFFFCh
0x1400236b6  add     edi, 0Ch
0x1400236b9  mov     edx, edi
0x1400236bb  call    cs:__imp_ExAllocatePool2
0x1400236c2  nop     dword ptr [rax+rax+00h]
0x1400236c7  mov     rbx, rax
0x1400236ca  test    rax, rax
0x1400236cd  jnz     short loc_1400236D6
0x1400236cf  mov     eax, 0C000009Ah
0x1400236d4  jmp     short loc_140023714
0x1400236d6  mov     ecx, [r14+18h]
0x1400236da  xor     eax, eax
0x1400236dc  test    ecx, ecx
0x1400236de  jz      short loc_1400236E8
0x1400236e0  cmp     ecx, 4
0x1400236e3  setnz   al
0x1400236e6  inc     eax
0x1400236e8  mov     [rbx], eax
0x1400236ea  lea     r9, [rbx+4]; struct _MBB_STRING *
0x1400236ee  lea     rax, [rbp+57h+var_70]
0x1400236f2  mov     dword ptr [rsp+0D0h+Size], esi; Size
0x1400236f6  mov     r8d, 0Ch; unsigned int
0x1400236fc  mov     [rsp+0D0h+Src], rax; Src
0x140023701  mov     edx, edi; unsigned int
0x140023703  mov     rcx, rbx; unsigned __int8 *
0x140023706  call    ?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z; MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)
0x14002370b  mov     [r15], rbx
0x14002370e  xor     eax, eax
0x140023710  mov     [r12], edi
0x140023714  mov     rcx, [rbp+57h+var_40]
0x140023718  xor     rcx, rsp; StackCookie
0x14002371b  call    __security_check_cookie
0x140023720  add     rsp, 0A0h
0x140023727  pop     r15
0x140023729  pop     r14
0x14002372b  pop     r12
0x14002372d  pop     rdi
0x14002372e  pop     rsi
0x14002372f  pop     rbx
0x140023730  pop     rbp
0x140023731  retn
```
