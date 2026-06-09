# PiiFilterpAddProfiles(_PII_FILTER *)

- ea: `0x18005a904`
- end: `0x18005ab8c`
- name: `?PiiFilterpAddProfiles@@YAJPEAU_PII_FILTER@@@Z`
- size: `648`
- prototype: `__int64 __fastcall(struct _PII_FILTER *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800505a8`

## callees

- `0x180002790`
- `0x18000279c`
- `0x180002874`
- `0x180042338`
- `0x180051b98`
- `0x1800520f8`
- `0x1800521bc`
- `0x18005a860`
- `0x18005a904`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005aabe`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005aabe`
- `ntdll!RtlAllocateHeap` at `0x18005a94c`
- `ntdll!RtlAllocateHeap` at `0x18005a976`
- `ntdll!RtlAllocateHeap` at `0x18005a94c`
- `ntdll!RtlAllocateHeap` at `0x18005a976`
- `ntdll!RtlFreeHeap` at `0x18005a9d8`
- `ntdll!RtlFreeHeap` at `0x18005ab14`
- `ntdll!RtlFreeHeap` at `0x18005ab31`
- `ntdll!RtlFreeHeap` at `0x18005ab4e`
- `ntdll!RtlFreeHeap` at `0x18005a9d8`
- `ntdll!RtlFreeHeap` at `0x18005ab14`
- `ntdll!RtlFreeHeap` at `0x18005ab31`
- `ntdll!RtlFreeHeap` at `0x18005ab4e`
- `ntdll!ZwClose` at `0x18005a9b7`
- `ntdll!ZwClose` at `0x18005ab5d`
- `ntdll!ZwClose` at `0x18005ab6c`
- `ntdll!ZwClose` at `0x18005a9b7`
- `ntdll!ZwClose` at `0x18005ab5d`
- `ntdll!ZwClose` at `0x18005ab6c`
- `ntdll!ZwEnumerateKey` at `0x18005aa22`
- `ntdll!ZwEnumerateKey` at `0x18005aa22`

## string_xrefs

- `0x18005aa7f`: `ProfileImagePath`
- `0x18005a991`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`

## pseudocode

```c
__int64 __fastcall PiiFilterpAddProfiles(struct _PII_FILTER *this)
{
  wchar_t *v2; // rdi
  WCHAR *Heap; // rsi
  int v4; // ebx
  PVOID v5; // r14
  ULONG i; // r12d
  NTSTATUS v7; // eax
  int v8; // ebx
  int v9; // eax
  wchar_t *v10; // rax
  const unsigned __int16 *v11; // rdx
  wchar_t *String; // [rsp+30h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+88h] [rbp+48h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp+50h] BYREF
  HANDLE KeyHandle; // [rsp+98h] [rbp+58h] BYREF

  ResultLength = 0;
  Handle = 0;
  KeyHandle = 0;
  v2 = 0;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x218u);
  if ( Heap )
  {
    v5 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x218u);
    if ( v5 )
    {
      v4 = AslRegistryOpenKey(
             &KeyHandle,
             L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
             8u);
      if ( v4 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          if ( Handle )
          {
            ZwClose(Handle);
            Handle = 0;
          }
          if ( v2 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
          String = 0;
          v2 = 0;
          memset_0(v5, 0, 0x218u);
          memset_0(Heap, 0, 0x218u);
          v7 = ZwEnumerateKey(KeyHandle, i, KeyBasicInformation, Heap, 0x217u, &ResultLength);
          if ( v7 == -2147483622 )
            break;
          if ( v7 >= 0 )
          {
            v8 = 0;
            while ( wcsicmp(Heap + 8, off_18006C230[v8]) )
            {
              if ( (unsigned int)++v8 >= 3 )
              {
                if ( AslRegistryOpenSubKey(&Handle, KeyHandle, Heap + 8) >= 0 )
                {
                  v9 = AslRegistryGetString(&String, Handle, L"ProfileImagePath");
                  v2 = String;
                  if ( v9 >= 0 )
                  {
                    wcslwr(String);
                    v4 = PiiFilterpAddItemSorted(this, v2, L"%USERPROFILE%");
                    if ( v4 < 0 )
                      goto LABEL_24;
                    v10 = wcsrchr(v2, 0x5Cu);
                    if ( v10 )
                    {
                      if ( v10[1] )
                      {
                        v4 = RtlNameValueArray::Insert(
                               (struct _PII_FILTER *)((char *)this + 48),
                               v11,
                               v10 + 1,
                               L"%USERNAME%",
                               *((_QWORD *)this + 8));
                        if ( v4 < 0 )
                          goto LABEL_24;
                      }
                    }
                  }
                }
                break;
              }
            }
          }
        }
        v4 = 0;
      }
    }
    else
    {
      v4 = -1073741801;
    }
LABEL_24:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    if ( v5 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  }
  else
  {
    v4 = -1073741801;
  }
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005a904  mov     [rsp-38h+arg_0], rbx
0x18005a909  push    rbp
0x18005a90a  push    rsi
0x18005a90b  push    rdi
0x18005a90c  push    r12
0x18005a90e  push    r13
0x18005a910  push    r14
0x18005a912  push    r15
0x18005a914  mov     rbp, rsp
0x18005a917  sub     rsp, 40h
0x18005a91b  xor     r15d, r15d
0x18005a91e  mov     r13, rcx
0x18005a921  mov     [rbp+arg_8], r15d
0x18005a925  mov     r14d, 218h
0x18005a92b  mov     [rbp+Handle], r15
0x18005a92f  mov     r8d, r14d; Size
0x18005a932  mov     [rbp+KeyHandle], r15
0x18005a936  mov     edi, r15d
0x18005a939  mov     rcx, gs:60h
0x18005a942  lea     ebx, [r15+8]
0x18005a946  mov     edx, ebx; Flags
0x18005a948  mov     rcx, [rcx+30h]; HeapHandle
0x18005a94c  call    cs:__imp_RtlAllocateHeap
0x18005a952  mov     rsi, rax
0x18005a955  test    rax, rax
0x18005a958  jnz     short loc_18005A964
0x18005a95a  mov     ebx, 0C0000017h
0x18005a95f  jmp     loc_18005AB37
0x18005a964  mov     rcx, gs:60h
0x18005a96d  mov     r8, r14; Size
0x18005a970  mov     edx, ebx; Flags
0x18005a972  mov     rcx, [rcx+30h]; HeapHandle
0x18005a976  call    cs:__imp_RtlAllocateHeap
0x18005a97c  mov     r14, rax
0x18005a97f  test    rax, rax
0x18005a982  jnz     short loc_18005A98E
0x18005a984  mov     ebx, 0C0000017h
0x18005a989  jmp     loc_18005AB02
0x18005a98e  mov     r8d, ebx
0x18005a991  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x18005a998  lea     rcx, [rbp+KeyHandle]
0x18005a99c  call    AslRegistryOpenKey
0x18005a9a1  mov     ebx, eax
0x18005a9a3  test    eax, eax
0x18005a9a5  js      loc_18005AB02
0x18005a9ab  mov     r12d, r15d
0x18005a9ae  mov     rcx, [rbp+Handle]; Handle
0x18005a9b2  test    rcx, rcx
0x18005a9b5  jz      short loc_18005A9C1
0x18005a9b7  call    cs:__imp_ZwClose
0x18005a9bd  mov     [rbp+Handle], r15
0x18005a9c1  test    rdi, rdi
0x18005a9c4  jz      short loc_18005A9DE
0x18005a9c6  mov     rcx, gs:60h
0x18005a9cf  mov     r8, rdi; P
0x18005a9d2  xor     edx, edx; Flags
0x18005a9d4  mov     rcx, [rcx+30h]; HeapHandle
0x18005a9d8  call    cs:__imp_RtlFreeHeap
0x18005a9de  mov     ebx, 218h
0x18005a9e3  mov     [rbp+String], r15
0x18005a9e7  mov     r8d, ebx; Size
0x18005a9ea  xor     edx, edx; Val
0x18005a9ec  mov     rcx, r14; void *
0x18005a9ef  mov     rdi, r15
0x18005a9f2  call    memset_0
0x18005a9f7  mov     r8d, ebx; Size
0x18005a9fa  xor     edx, edx; Val
0x18005a9fc  mov     rcx, rsi; void *
0x18005a9ff  call    memset_0
0x18005aa04  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18005aa08  lea     rax, [rbp+arg_8]
0x18005aa0c  mov     [rsp+40h+ResultLength], rax; ResultLength
0x18005aa11  mov     r9, rsi; KeyInformation
0x18005aa14  xor     r8d, r8d; KeyInformationClass
0x18005aa17  mov     [rsp+40h+Length], 217h; Length
0x18005aa1f  mov     edx, r12d; Index
0x18005aa22  call    cs:__imp_ZwEnumerateKey
0x18005aa28  cmp     eax, 8000001Ah
0x18005aa2d  jz      loc_18005AAFF
0x18005aa33  test    eax, eax
0x18005aa35  js      loc_18005AAF7
0x18005aa3b  mov     ebx, r15d
0x18005aa3e  lea     rax, off_18006C230; "s-1-5-18"
0x18005aa45  mov     edx, ebx
0x18005aa47  lea     rcx, [rsi+10h]; String1
0x18005aa4b  mov     rdx, [rax+rdx*8]; String2
0x18005aa4f  call    _wcsicmp
0x18005aa54  test    eax, eax
0x18005aa56  jz      loc_18005AAF4
0x18005aa5c  inc     ebx
0x18005aa5e  cmp     ebx, 3
0x18005aa61  jb      short loc_18005AA3E
0x18005aa63  mov     rdx, [rbp+KeyHandle]
0x18005aa67  lea     r8, [rsi+10h]
0x18005aa6b  lea     rcx, [rbp+Handle]; KeyHandle
0x18005aa6f  call    AslRegistryOpenSubKey
0x18005aa74  xor     r15d, r15d
0x18005aa77  test    eax, eax
0x18005aa79  js      short loc_18005AAF7
0x18005aa7b  mov     rdx, [rbp+Handle]
0x18005aa7f  lea     r8, aProfileimagepa; "ProfileImagePath"
0x18005aa86  lea     rcx, [rbp+String]
0x18005aa8a  call    AslRegistryGetString
0x18005aa8f  mov     rdi, [rbp+String]
0x18005aa93  test    eax, eax
0x18005aa95  js      short loc_18005AAF7
0x18005aa97  mov     rcx, rdi; String
0x18005aa9a  call    _wcslwr
0x18005aa9f  lea     r8, aUserprofile; "%USERPROFILE%"
0x18005aaa6  mov     rdx, rdi; unsigned __int16 *
0x18005aaa9  mov     rcx, r13; this
0x18005aaac  call    ?PiiFilterpAddItemSorted@@YAJPEAU_PII_FILTER@@PEBG1@Z; PiiFilterpAddItemSorted(_PII_FILTER *,ushort const *,ushort const *)
0x18005aab1  mov     ebx, eax
0x18005aab3  test    eax, eax
0x18005aab5  js      short loc_18005AB02
0x18005aab7  lea     edx, [r15+5Ch]; Ch
0x18005aabb  mov     rcx, rdi; Str
0x18005aabe  call    cs:__imp_wcsrchr
0x18005aac4  test    rax, rax
0x18005aac7  jz      short loc_18005AAF7
0x18005aac9  lea     r8, [rax+2]; unsigned __int16 *
0x18005aacd  cmp     [r8], r15w
0x18005aad1  jz      short loc_18005AAF7
0x18005aad3  lea     rcx, [r13+30h]; this
0x18005aad7  mov     rax, [rcx+10h]
0x18005aadb  lea     r9, aUsername; "%USERNAME%"
0x18005aae2  mov     qword ptr [rsp+40h+Length], rax; unsigned __int64
0x18005aae7  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x18005aaec  mov     ebx, eax
0x18005aaee  test    eax, eax
0x18005aaf0  js      short loc_18005AB02
0x18005aaf2  jmp     short loc_18005AAF7
0x18005aaf4  xor     r15d, r15d
0x18005aaf7  inc     r12d
0x18005aafa  jmp     loc_18005A9AE
0x18005aaff  mov     ebx, r15d
0x18005ab02  mov     rcx, gs:60h
0x18005ab0b  mov     r8, rsi; P
0x18005ab0e  xor     edx, edx; Flags
0x18005ab10  mov     rcx, [rcx+30h]; HeapHandle
0x18005ab14  call    cs:__imp_RtlFreeHeap
0x18005ab1a  test    r14, r14
0x18005ab1d  jz      short loc_18005AB37
0x18005ab1f  mov     rcx, gs:60h
0x18005ab28  mov     r8, r14; P
0x18005ab2b  xor     edx, edx; Flags
0x18005ab2d  mov     rcx, [rcx+30h]; HeapHandle
0x18005ab31  call    cs:__imp_RtlFreeHeap
0x18005ab37  test    rdi, rdi
0x18005ab3a  jz      short loc_18005AB54
0x18005ab3c  mov     rcx, gs:60h
0x18005ab45  mov     r8, rdi; P
0x18005ab48  xor     edx, edx; Flags
0x18005ab4a  mov     rcx, [rcx+30h]; HeapHandle
0x18005ab4e  call    cs:__imp_RtlFreeHeap
0x18005ab54  mov     rcx, [rbp+KeyHandle]; Handle
0x18005ab58  test    rcx, rcx
0x18005ab5b  jz      short loc_18005AB63
0x18005ab5d  call    cs:__imp_ZwClose
0x18005ab63  mov     rcx, [rbp+Handle]; Handle
0x18005ab67  test    rcx, rcx
0x18005ab6a  jz      short loc_18005AB72
0x18005ab6c  call    cs:__imp_ZwClose
0x18005ab72  mov     eax, ebx
0x18005ab74  mov     rbx, [rsp+40h+arg_0]
0x18005ab7c  add     rsp, 40h
0x18005ab80  pop     r15
0x18005ab82  pop     r14
0x18005ab84  pop     r13
0x18005ab86  pop     r12
0x18005ab88  pop     rdi
0x18005ab89  pop     rsi
0x18005ab8a  pop     rbp
0x18005ab8b  retn
```
