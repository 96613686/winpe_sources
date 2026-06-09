# Broker::BrokerBase::BrokerIsRegistered(void)

- ea: `0x18000d060`
- end: `0x18000d262`
- name: `?BrokerIsRegistered@BrokerBase@Broker@@QEAA_NXZ`
- size: `514`
- prototype: `bool __fastcall(Broker::BrokerBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c4c0`

## callees

- `0x180005b50`
- `0x18000cfac`
- `0x18000d060`
- `0x18000d268`

## import_xrefs

- `ntdll!RtlStringFromGUIDEx` at `0x18000d1c5`
- `ntdll!RtlStringFromGUIDEx` at `0x18000d1c5`
- `ntdll!RtlFreeHeap` at `0x18000d241`
- `ntdll!RtlFreeHeap` at `0x18000d241`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000d0de`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000d0de`
- `ntdll!NtClose` at `0x18000d224`
- `ntdll!NtClose` at `0x18000d224`
- `ntdll!NtOpenKey` at `0x18000d20a`
- `ntdll!NtOpenKey` at `0x18000d20a`
- `ntdll!RtlAllocateHeap` at `0x18000d109`
- `ntdll!RtlAllocateHeap` at `0x18000d109`

## string_xrefs

- `0x18000d0b8`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\BackgroundModel\Brokers`

## pseudocode

```c
char __fastcall Broker::BrokerBase::BrokerIsRegistered(Broker::BrokerBase *this)
{
  char v2; // si
  SIZE_T v3; // rdi
  WCHAR *Heap; // rax
  WCHAR *v5; // rbx
  int v6; // eax
  PWSTR Buffer; // rdx
  unsigned __int64 v8; // r9
  __int16 v9; // cx
  int v10; // r10d
  unsigned __int64 v11; // r9
  WCHAR *v12; // r8
  SIZE_T v13; // rdi
  struct _UNICODE_STRING v15; // [rsp+20h] [rbp-60h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  __int128 v17; // [rsp+40h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+A8h] [rbp+28h] BYREF

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *((_QWORD *)this + 1));
  KeyHandle = 0;
  v2 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v17 = 0;
  DestinationString = 0;
  v15 = 0;
  if ( RtlInitUnicodeStringEx(
         &DestinationString,
         L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\BackgroundModel\\Brokers") < 0 )
  {
    v5 = 0;
  }
  else
  {
    v3 = (unsigned __int16)(DestinationString.Length + 80);
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
    v5 = Heap;
    if ( Heap )
    {
      v15.Length = 0;
      v15.Buffer = Heap;
      v15.MaximumLength = v3;
      LODWORD(v17) = 5111808;
      *((_QWORD *)&v17 + 1) = (char *)Heap + DestinationString.Length + 2;
      if ( (int)RtlUnicodeStringValidateWorker(&v15) >= 0 )
      {
        v6 = RtlUnicodeStringValidateWorker(&DestinationString);
        v9 = 0;
        v10 = v6;
        if ( v6 >= 0 )
        {
          Buffer = DestinationString.Buffer;
          v10 = 0;
          v11 = v8 >> 1;
          v12 = v5;
          v13 = v3 >> 1;
          if ( v13 )
          {
            while ( v11 )
            {
              --v11;
              *v12++ = *Buffer++;
              ++v9;
              if ( !--v13 )
                goto LABEL_11;
            }
          }
          else
          {
LABEL_11:
            if ( v11 )
              v10 = -2147483643;
          }
        }
        v15.Length = 2 * v9;
        if ( v10 >= 0
          && (int)RtlUnicodeStringCatString(&v15, Buffer) >= 0
          && (int)RtlStringFromGUIDEx(*((_QWORD *)this + 1), &v17, 0) >= 0 )
        {
          v15.Length += v17;
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &v15;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
            v2 = 1;
        }
      }
    }
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  return v2;
}

```

## disassembly

```asm
0x18000d060  mov     [rsp-18h+arg_0], rbx
0x18000d065  mov     [rsp-18h+arg_10], rsi
0x18000d06a  push    rbp
0x18000d06b  push    rdi
0x18000d06c  push    r14
0x18000d06e  mov     rbp, rsp
0x18000d071  sub     rsp, 80h
0x18000d078  mov     r14, rcx
0x18000d07b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d082  test    dword ptr [rcx+1Ch], 800h
0x18000d089  jz      short loc_18000D0AA
0x18000d08b  cmp     byte ptr [rcx+19h], 5
0x18000d08f  jb      short loc_18000D0AA
0x18000d091  mov     r9, [r14+8]
0x18000d095  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x18000d09c  mov     rcx, [rcx+10h]
0x18000d0a0  mov     edx, 11h
0x18000d0a5  call    WPP_SF__guid_
0x18000d0aa  xorps   xmm0, xmm0
0x18000d0ad  mov     [rbp+KeyHandle], 0
0x18000d0b5  xorps   xmm1, xmm1
0x18000d0b8  lea     rdx, SourceString; "\\Registry\\Machine\\Software\\Microsof"...
0x18000d0bf  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000d0c3  xor     sil, sil
0x18000d0c6  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000d0ca  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000d0ce  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d0d2  movups  [rbp+var_40], xmm0
0x18000d0d6  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x18000d0da  movups  xmmword ptr [rbp+var_60.Length], xmm0
0x18000d0de  call    cs:__imp_RtlInitUnicodeStringEx
0x18000d0e4  test    eax, eax
0x18000d0e6  js      loc_18000D219
0x18000d0ec  movzx   eax, [rbp+DestinationString.Length]
0x18000d0f0  xor     edx, edx; Flags
0x18000d0f2  mov     rcx, gs:60h
0x18000d0fb  add     ax, 50h ; 'P'
0x18000d0ff  movzx   edi, ax
0x18000d102  mov     r8d, edi; Size
0x18000d105  mov     rcx, [rcx+30h]; HeapHandle
0x18000d109  call    cs:__imp_RtlAllocateHeap
0x18000d10f  mov     rbx, rax
0x18000d112  test    rax, rax
0x18000d115  jz      loc_18000D21B
0x18000d11b  movzx   r9d, [rbp+DestinationString.Length]
0x18000d120  xor     ecx, ecx
0x18000d122  mov     [rbp+var_60.Length], cx
0x18000d126  mov     [rbp+var_60.Buffer], rax
0x18000d12a  mov     [rbp+var_60.MaximumLength], di
0x18000d12e  lea     rcx, [r9+2]
0x18000d132  mov     dword ptr [rbp+var_40], 4E0000h
0x18000d139  add     rcx, rax
0x18000d13c  mov     qword ptr [rbp+var_40+8], rcx
0x18000d140  lea     rcx, [rbp+var_60]
0x18000d144  call    RtlUnicodeStringValidateWorker
0x18000d149  test    eax, eax
0x18000d14b  js      loc_18000D21B
0x18000d151  lea     rcx, [rbp+DestinationString]
0x18000d155  call    RtlUnicodeStringValidateWorker
0x18000d15a  xor     ecx, ecx
0x18000d15c  mov     r10d, eax
0x18000d15f  test    eax, eax
0x18000d161  js      short loc_18000D1A1
0x18000d163  mov     rdx, [rbp+DestinationString.Buffer]
0x18000d167  xor     r10d, r10d
0x18000d16a  shr     r9, 1
0x18000d16d  mov     r8, rbx
0x18000d170  shr     rdi, 1
0x18000d173  jz      short loc_18000D195
0x18000d175  test    r9, r9
0x18000d178  jz      short loc_18000D1A1
0x18000d17a  movzx   eax, word ptr [rdx]
0x18000d17d  dec     r9
0x18000d180  mov     [r8], ax
0x18000d184  add     rdx, 2; unsigned __int16 *
0x18000d188  add     r8, 2
0x18000d18c  inc     rcx
0x18000d18f  sub     rdi, 1
0x18000d193  jnz     short loc_18000D175
0x18000d195  test    r9, r9
0x18000d198  mov     eax, 80000005h
0x18000d19d  cmovnz  r10d, eax
0x18000d1a1  add     cx, cx
0x18000d1a4  mov     [rbp+var_60.Length], cx
0x18000d1a8  test    r10d, r10d
0x18000d1ab  js      short loc_18000D21B
0x18000d1ad  lea     rcx, [rbp+var_60]; struct _UNICODE_STRING *
0x18000d1b1  call    ?RtlUnicodeStringCatString@@YAJPEAU_UNICODE_STRING@@PEBG@Z; RtlUnicodeStringCatString(_UNICODE_STRING *,ushort const *)
0x18000d1b6  test    eax, eax
0x18000d1b8  js      short loc_18000D21B
0x18000d1ba  mov     rcx, [r14+8]
0x18000d1be  lea     rdx, [rbp+var_40]
0x18000d1c2  xor     r8d, r8d
0x18000d1c5  call    cs:__imp_RtlStringFromGUIDEx
0x18000d1cb  test    eax, eax
0x18000d1cd  js      short loc_18000D21B
0x18000d1cf  movzx   eax, word ptr [rbp+var_40]
0x18000d1d3  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000d1d7  add     [rbp+var_60.Length], ax
0x18000d1db  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18000d1df  lea     rax, [rbp+var_60]
0x18000d1e3  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000d1ea  xorps   xmm0, xmm0
0x18000d1ed  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000d1f1  mov     edx, 20019h; DesiredAccess
0x18000d1f6  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18000d1fe  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18000d205  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d20a  call    cs:__imp_NtOpenKey
0x18000d210  test    eax, eax
0x18000d212  js      short loc_18000D21B
0x18000d214  mov     sil, 1
0x18000d217  jmp     short loc_18000D21B
0x18000d219  xor     ebx, ebx
0x18000d21b  mov     rcx, [rbp+KeyHandle]; Handle
0x18000d21f  test    rcx, rcx
0x18000d222  jz      short loc_18000D22A
0x18000d224  call    cs:__imp_NtClose
0x18000d22a  test    rbx, rbx
0x18000d22d  jz      short loc_18000D247
0x18000d22f  mov     rcx, gs:60h
0x18000d238  mov     r8, rbx; P
0x18000d23b  xor     edx, edx; Flags
0x18000d23d  mov     rcx, [rcx+30h]; HeapHandle
0x18000d241  call    cs:__imp_RtlFreeHeap
0x18000d247  lea     r11, [rsp+80h+var_s0]
0x18000d24f  mov     al, sil
0x18000d252  mov     rbx, [r11+20h]
0x18000d256  mov     rsi, [r11+30h]
0x18000d25a  mov     rsp, r11
0x18000d25d  pop     r14
0x18000d25f  pop     rdi
0x18000d260  pop     rbp
0x18000d261  retn
```
