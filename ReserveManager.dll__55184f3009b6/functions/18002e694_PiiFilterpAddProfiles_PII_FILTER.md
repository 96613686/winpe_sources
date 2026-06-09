# PiiFilterpAddProfiles(_PII_FILTER *)

- ea: `0x18002e694`
- end: `0x18002e91c`
- name: `?PiiFilterpAddProfiles@@YAJPEAU_PII_FILTER@@@Z`
- size: `648`
- prototype: `__int64 __fastcall(struct _PII_FILTER *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028510`

## callees

- `0x180004264`
- `0x180004270`
- `0x1800042f4`
- `0x18002e324`
- `0x18002e5e0`
- `0x18002e694`
- `0x180030fb4`
- `0x1800313a4`
- `0x18003143c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002e84e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002e84e`
- `ntdll!RtlAllocateHeap` at `0x18002e6dc`
- `ntdll!RtlAllocateHeap` at `0x18002e706`
- `ntdll!RtlAllocateHeap` at `0x18002e6dc`
- `ntdll!RtlAllocateHeap` at `0x18002e706`
- `ntdll!RtlFreeHeap` at `0x18002e768`
- `ntdll!RtlFreeHeap` at `0x18002e8a4`
- `ntdll!RtlFreeHeap` at `0x18002e8c1`
- `ntdll!RtlFreeHeap` at `0x18002e8de`
- `ntdll!RtlFreeHeap` at `0x18002e768`
- `ntdll!RtlFreeHeap` at `0x18002e8a4`
- `ntdll!RtlFreeHeap` at `0x18002e8c1`
- `ntdll!RtlFreeHeap` at `0x18002e8de`
- `ntdll!ZwEnumerateKey` at `0x18002e7b2`
- `ntdll!ZwEnumerateKey` at `0x18002e7b2`
- `ntdll!ZwClose` at `0x18002e747`
- `ntdll!ZwClose` at `0x18002e8ed`
- `ntdll!ZwClose` at `0x18002e8fc`
- `ntdll!ZwClose` at `0x18002e747`
- `ntdll!ZwClose` at `0x18002e8ed`
- `ntdll!ZwClose` at `0x18002e8fc`

## string_xrefs

- `0x18002e721`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`
- `0x18002e80f`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall PiiFilterpAddProfiles(struct _PII_FILTER *this)
{
  wchar_t *v2; // rdi
  wchar_t *Heap; // rsi
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
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x218u);
  if ( Heap )
  {
    v5 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x218u);
    if ( v5 )
    {
      v4 = AslRegistryOpenKey(&KeyHandle);
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
            while ( wcsicmp(Heap + 8, off_180035AD0[v8]) )
            {
              if ( (unsigned int)++v8 >= 3 )
              {
                if ( (int)AslRegistryOpenSubKey(&Handle) >= 0 )
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
0x18002e694  mov     [rsp-38h+arg_0], rbx
0x18002e699  push    rbp
0x18002e69a  push    rsi
0x18002e69b  push    rdi
0x18002e69c  push    r12
0x18002e69e  push    r13
0x18002e6a0  push    r14
0x18002e6a2  push    r15
0x18002e6a4  mov     rbp, rsp
0x18002e6a7  sub     rsp, 40h
0x18002e6ab  xor     r15d, r15d
0x18002e6ae  mov     r13, rcx
0x18002e6b1  mov     [rbp+arg_8], r15d
0x18002e6b5  mov     r14d, 218h
0x18002e6bb  mov     [rbp+Handle], r15
0x18002e6bf  mov     r8d, r14d; Size
0x18002e6c2  mov     [rbp+KeyHandle], r15
0x18002e6c6  mov     edi, r15d
0x18002e6c9  mov     rcx, gs:60h
0x18002e6d2  lea     ebx, [r15+8]
0x18002e6d6  mov     edx, ebx; Flags
0x18002e6d8  mov     rcx, [rcx+30h]; HeapHandle
0x18002e6dc  call    cs:__imp_RtlAllocateHeap
0x18002e6e2  mov     rsi, rax
0x18002e6e5  test    rax, rax
0x18002e6e8  jnz     short loc_18002E6F4
0x18002e6ea  mov     ebx, 0C0000017h
0x18002e6ef  jmp     loc_18002E8C7
0x18002e6f4  mov     rcx, gs:60h
0x18002e6fd  mov     r8, r14; Size
0x18002e700  mov     edx, ebx; Flags
0x18002e702  mov     rcx, [rcx+30h]; HeapHandle
0x18002e706  call    cs:__imp_RtlAllocateHeap
0x18002e70c  mov     r14, rax
0x18002e70f  test    rax, rax
0x18002e712  jnz     short loc_18002E71E
0x18002e714  mov     ebx, 0C0000017h
0x18002e719  jmp     loc_18002E892
0x18002e71e  mov     r8d, ebx
0x18002e721  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x18002e728  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18002e72c  call    AslRegistryOpenKey
0x18002e731  mov     ebx, eax
0x18002e733  test    eax, eax
0x18002e735  js      loc_18002E892
0x18002e73b  mov     r12d, r15d
0x18002e73e  mov     rcx, [rbp+Handle]; Handle
0x18002e742  test    rcx, rcx
0x18002e745  jz      short loc_18002E751
0x18002e747  call    cs:__imp_ZwClose
0x18002e74d  mov     [rbp+Handle], r15
0x18002e751  test    rdi, rdi
0x18002e754  jz      short loc_18002E76E
0x18002e756  mov     rcx, gs:60h
0x18002e75f  mov     r8, rdi; P
0x18002e762  xor     edx, edx; Flags
0x18002e764  mov     rcx, [rcx+30h]; HeapHandle
0x18002e768  call    cs:__imp_RtlFreeHeap
0x18002e76e  mov     ebx, 218h
0x18002e773  mov     [rbp+String], r15
0x18002e777  mov     r8d, ebx; Size
0x18002e77a  xor     edx, edx; Val
0x18002e77c  mov     rcx, r14; void *
0x18002e77f  mov     rdi, r15
0x18002e782  call    memset_0
0x18002e787  mov     r8d, ebx; Size
0x18002e78a  xor     edx, edx; Val
0x18002e78c  mov     rcx, rsi; void *
0x18002e78f  call    memset_0
0x18002e794  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18002e798  lea     rax, [rbp+arg_8]
0x18002e79c  mov     [rsp+40h+ResultLength], rax; ResultLength
0x18002e7a1  mov     r9, rsi; KeyInformation
0x18002e7a4  xor     r8d, r8d; KeyInformationClass
0x18002e7a7  mov     [rsp+40h+Length], 217h; Length
0x18002e7af  mov     edx, r12d; Index
0x18002e7b2  call    cs:__imp_ZwEnumerateKey
0x18002e7b8  cmp     eax, 8000001Ah
0x18002e7bd  jz      loc_18002E88F
0x18002e7c3  test    eax, eax
0x18002e7c5  js      loc_18002E887
0x18002e7cb  mov     ebx, r15d
0x18002e7ce  lea     rax, off_180035AD0; "s-1-5-18"
0x18002e7d5  mov     edx, ebx
0x18002e7d7  lea     rcx, [rsi+10h]; String1
0x18002e7db  mov     rdx, [rax+rdx*8]; String2
0x18002e7df  call    _wcsicmp
0x18002e7e4  test    eax, eax
0x18002e7e6  jz      loc_18002E884
0x18002e7ec  inc     ebx
0x18002e7ee  cmp     ebx, 3
0x18002e7f1  jb      short loc_18002E7CE
0x18002e7f3  mov     rdx, [rbp+KeyHandle]
0x18002e7f7  lea     r8, [rsi+10h]
0x18002e7fb  lea     rcx, [rbp+Handle]; KeyHandle
0x18002e7ff  call    AslRegistryOpenSubKey
0x18002e804  xor     r15d, r15d
0x18002e807  test    eax, eax
0x18002e809  js      short loc_18002E887
0x18002e80b  mov     rdx, [rbp+Handle]
0x18002e80f  lea     r8, aProfileimagepa; "ProfileImagePath"
0x18002e816  lea     rcx, [rbp+String]
0x18002e81a  call    AslRegistryGetString
0x18002e81f  mov     rdi, [rbp+String]
0x18002e823  test    eax, eax
0x18002e825  js      short loc_18002E887
0x18002e827  mov     rcx, rdi; String
0x18002e82a  call    _wcslwr
0x18002e82f  lea     r8, aUserprofile; "%USERPROFILE%"
0x18002e836  mov     rdx, rdi; unsigned __int16 *
0x18002e839  mov     rcx, r13; this
0x18002e83c  call    ?PiiFilterpAddItemSorted@@YAJPEAU_PII_FILTER@@PEBG1@Z; PiiFilterpAddItemSorted(_PII_FILTER *,ushort const *,ushort const *)
0x18002e841  mov     ebx, eax
0x18002e843  test    eax, eax
0x18002e845  js      short loc_18002E892
0x18002e847  lea     edx, [r15+5Ch]; Ch
0x18002e84b  mov     rcx, rdi; Str
0x18002e84e  call    cs:__imp_wcsrchr
0x18002e854  test    rax, rax
0x18002e857  jz      short loc_18002E887
0x18002e859  lea     r8, [rax+2]; unsigned __int16 *
0x18002e85d  cmp     [r8], r15w
0x18002e861  jz      short loc_18002E887
0x18002e863  lea     rcx, [r13+30h]; this
0x18002e867  mov     rax, [rcx+10h]
0x18002e86b  lea     r9, aUsername; "%USERNAME%"
0x18002e872  mov     qword ptr [rsp+40h+Length], rax; unsigned __int64
0x18002e877  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x18002e87c  mov     ebx, eax
0x18002e87e  test    eax, eax
0x18002e880  js      short loc_18002E892
0x18002e882  jmp     short loc_18002E887
0x18002e884  xor     r15d, r15d
0x18002e887  inc     r12d
0x18002e88a  jmp     loc_18002E73E
0x18002e88f  mov     ebx, r15d
0x18002e892  mov     rcx, gs:60h
0x18002e89b  mov     r8, rsi; P
0x18002e89e  xor     edx, edx; Flags
0x18002e8a0  mov     rcx, [rcx+30h]; HeapHandle
0x18002e8a4  call    cs:__imp_RtlFreeHeap
0x18002e8aa  test    r14, r14
0x18002e8ad  jz      short loc_18002E8C7
0x18002e8af  mov     rcx, gs:60h
0x18002e8b8  mov     r8, r14; P
0x18002e8bb  xor     edx, edx; Flags
0x18002e8bd  mov     rcx, [rcx+30h]; HeapHandle
0x18002e8c1  call    cs:__imp_RtlFreeHeap
0x18002e8c7  test    rdi, rdi
0x18002e8ca  jz      short loc_18002E8E4
0x18002e8cc  mov     rcx, gs:60h
0x18002e8d5  mov     r8, rdi; P
0x18002e8d8  xor     edx, edx; Flags
0x18002e8da  mov     rcx, [rcx+30h]; HeapHandle
0x18002e8de  call    cs:__imp_RtlFreeHeap
0x18002e8e4  mov     rcx, [rbp+KeyHandle]; Handle
0x18002e8e8  test    rcx, rcx
0x18002e8eb  jz      short loc_18002E8F3
0x18002e8ed  call    cs:__imp_ZwClose
0x18002e8f3  mov     rcx, [rbp+Handle]; Handle
0x18002e8f7  test    rcx, rcx
0x18002e8fa  jz      short loc_18002E902
0x18002e8fc  call    cs:__imp_ZwClose
0x18002e902  mov     eax, ebx
0x18002e904  mov     rbx, [rsp+40h+arg_0]
0x18002e90c  add     rsp, 40h
0x18002e910  pop     r15
0x18002e912  pop     r14
0x18002e914  pop     r13
0x18002e916  pop     r12
0x18002e918  pop     rdi
0x18002e919  pop     rsi
0x18002e91a  pop     rbp
0x18002e91b  retn
```
