# PiiFilterpAddProfiles(_PII_FILTER *)

- ea: `0x14001582c`
- end: `0x140015ab4`
- name: `?PiiFilterpAddProfiles@@YAJPEAU_PII_FILTER@@@Z`
- size: `648`
- prototype: `__int64 __fastcall(struct _PII_FILTER *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140011260`

## callees

- `0x140002618`
- `0x140002624`
- `0x1400026c0`
- `0x1400129e0`
- `0x140012f44`
- `0x140012fdc`
- `0x1400154cc`
- `0x140015788`
- `0x14001582c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400159e6`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400159e6`
- `ntdll!ZwEnumerateKey` at `0x14001594a`
- `ntdll!ZwEnumerateKey` at `0x14001594a`
- `ntdll!ZwClose` at `0x1400158df`
- `ntdll!ZwClose` at `0x140015a85`
- `ntdll!ZwClose` at `0x140015a94`
- `ntdll!ZwClose` at `0x1400158df`
- `ntdll!ZwClose` at `0x140015a85`
- `ntdll!ZwClose` at `0x140015a94`
- `ntdll!RtlFreeHeap` at `0x140015900`
- `ntdll!RtlFreeHeap` at `0x140015a3c`
- `ntdll!RtlFreeHeap` at `0x140015a59`
- `ntdll!RtlFreeHeap` at `0x140015a76`
- `ntdll!RtlFreeHeap` at `0x140015900`
- `ntdll!RtlFreeHeap` at `0x140015a3c`
- `ntdll!RtlFreeHeap` at `0x140015a59`
- `ntdll!RtlFreeHeap` at `0x140015a76`
- `ntdll!RtlAllocateHeap` at `0x140015874`
- `ntdll!RtlAllocateHeap` at `0x14001589e`
- `ntdll!RtlAllocateHeap` at `0x140015874`
- `ntdll!RtlAllocateHeap` at `0x14001589e`

## string_xrefs

- `0x1400158b9`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`
- `0x1400159a7`: `ProfileImagePath`

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
            while ( wcsicmp(Heap + 8, off_1400AA0E0[v8]) )
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
0x14001582c  mov     [rsp-38h+arg_0], rbx
0x140015831  push    rbp
0x140015832  push    rsi
0x140015833  push    rdi
0x140015834  push    r12
0x140015836  push    r13
0x140015838  push    r14
0x14001583a  push    r15
0x14001583c  mov     rbp, rsp
0x14001583f  sub     rsp, 40h
0x140015843  xor     r15d, r15d
0x140015846  mov     r13, rcx
0x140015849  mov     [rbp+arg_8], r15d
0x14001584d  mov     r14d, 218h
0x140015853  mov     [rbp+Handle], r15
0x140015857  mov     r8d, r14d; Size
0x14001585a  mov     [rbp+KeyHandle], r15
0x14001585e  mov     edi, r15d
0x140015861  mov     rcx, gs:60h
0x14001586a  lea     ebx, [r15+8]
0x14001586e  mov     edx, ebx; Flags
0x140015870  mov     rcx, [rcx+30h]; HeapHandle
0x140015874  call    cs:__imp_RtlAllocateHeap
0x14001587a  mov     rsi, rax
0x14001587d  test    rax, rax
0x140015880  jnz     short loc_14001588C
0x140015882  mov     ebx, 0C0000017h
0x140015887  jmp     loc_140015A5F
0x14001588c  mov     rcx, gs:60h
0x140015895  mov     r8, r14; Size
0x140015898  mov     edx, ebx; Flags
0x14001589a  mov     rcx, [rcx+30h]; HeapHandle
0x14001589e  call    cs:__imp_RtlAllocateHeap
0x1400158a4  mov     r14, rax
0x1400158a7  test    rax, rax
0x1400158aa  jnz     short loc_1400158B6
0x1400158ac  mov     ebx, 0C0000017h
0x1400158b1  jmp     loc_140015A2A
0x1400158b6  mov     r8d, ebx
0x1400158b9  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x1400158c0  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400158c4  call    AslRegistryOpenKey
0x1400158c9  mov     ebx, eax
0x1400158cb  test    eax, eax
0x1400158cd  js      loc_140015A2A
0x1400158d3  mov     r12d, r15d
0x1400158d6  mov     rcx, [rbp+Handle]; Handle
0x1400158da  test    rcx, rcx
0x1400158dd  jz      short loc_1400158E9
0x1400158df  call    cs:__imp_ZwClose
0x1400158e5  mov     [rbp+Handle], r15
0x1400158e9  test    rdi, rdi
0x1400158ec  jz      short loc_140015906
0x1400158ee  mov     rcx, gs:60h
0x1400158f7  mov     r8, rdi; P
0x1400158fa  xor     edx, edx; Flags
0x1400158fc  mov     rcx, [rcx+30h]; HeapHandle
0x140015900  call    cs:__imp_RtlFreeHeap
0x140015906  mov     ebx, 218h
0x14001590b  mov     [rbp+String], r15
0x14001590f  mov     r8d, ebx; Size
0x140015912  xor     edx, edx; Val
0x140015914  mov     rcx, r14; void *
0x140015917  mov     rdi, r15
0x14001591a  call    memset_0
0x14001591f  mov     r8d, ebx; Size
0x140015922  xor     edx, edx; Val
0x140015924  mov     rcx, rsi; void *
0x140015927  call    memset_0
0x14001592c  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140015930  lea     rax, [rbp+arg_8]
0x140015934  mov     [rsp+40h+ResultLength], rax; ResultLength
0x140015939  mov     r9, rsi; KeyInformation
0x14001593c  xor     r8d, r8d; KeyInformationClass
0x14001593f  mov     [rsp+40h+Length], 217h; Length
0x140015947  mov     edx, r12d; Index
0x14001594a  call    cs:__imp_ZwEnumerateKey
0x140015950  cmp     eax, 8000001Ah
0x140015955  jz      loc_140015A27
0x14001595b  test    eax, eax
0x14001595d  js      loc_140015A1F
0x140015963  mov     ebx, r15d
0x140015966  lea     rax, off_1400AA0E0; "s-1-5-18"
0x14001596d  mov     edx, ebx
0x14001596f  lea     rcx, [rsi+10h]; String1
0x140015973  mov     rdx, [rax+rdx*8]; String2
0x140015977  call    _wcsicmp
0x14001597c  test    eax, eax
0x14001597e  jz      loc_140015A1C
0x140015984  inc     ebx
0x140015986  cmp     ebx, 3
0x140015989  jb      short loc_140015966
0x14001598b  mov     rdx, [rbp+KeyHandle]
0x14001598f  lea     r8, [rsi+10h]
0x140015993  lea     rcx, [rbp+Handle]; KeyHandle
0x140015997  call    AslRegistryOpenSubKey
0x14001599c  xor     r15d, r15d
0x14001599f  test    eax, eax
0x1400159a1  js      short loc_140015A1F
0x1400159a3  mov     rdx, [rbp+Handle]
0x1400159a7  lea     r8, aProfileimagepa; "ProfileImagePath"
0x1400159ae  lea     rcx, [rbp+String]
0x1400159b2  call    AslRegistryGetString
0x1400159b7  mov     rdi, [rbp+String]
0x1400159bb  test    eax, eax
0x1400159bd  js      short loc_140015A1F
0x1400159bf  mov     rcx, rdi; String
0x1400159c2  call    _wcslwr
0x1400159c7  lea     r8, aUserprofile; "%USERPROFILE%"
0x1400159ce  mov     rdx, rdi; unsigned __int16 *
0x1400159d1  mov     rcx, r13; this
0x1400159d4  call    ?PiiFilterpAddItemSorted@@YAJPEAU_PII_FILTER@@PEBG1@Z; PiiFilterpAddItemSorted(_PII_FILTER *,ushort const *,ushort const *)
0x1400159d9  mov     ebx, eax
0x1400159db  test    eax, eax
0x1400159dd  js      short loc_140015A2A
0x1400159df  lea     edx, [r15+5Ch]; Ch
0x1400159e3  mov     rcx, rdi; Str
0x1400159e6  call    cs:__imp_wcsrchr
0x1400159ec  test    rax, rax
0x1400159ef  jz      short loc_140015A1F
0x1400159f1  lea     r8, [rax+2]; unsigned __int16 *
0x1400159f5  cmp     [r8], r15w
0x1400159f9  jz      short loc_140015A1F
0x1400159fb  lea     rcx, [r13+30h]; this
0x1400159ff  mov     rax, [rcx+10h]
0x140015a03  lea     r9, aUsername; "%USERNAME%"
0x140015a0a  mov     qword ptr [rsp+40h+Length], rax; unsigned __int64
0x140015a0f  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x140015a14  mov     ebx, eax
0x140015a16  test    eax, eax
0x140015a18  js      short loc_140015A2A
0x140015a1a  jmp     short loc_140015A1F
0x140015a1c  xor     r15d, r15d
0x140015a1f  inc     r12d
0x140015a22  jmp     loc_1400158D6
0x140015a27  mov     ebx, r15d
0x140015a2a  mov     rcx, gs:60h
0x140015a33  mov     r8, rsi; P
0x140015a36  xor     edx, edx; Flags
0x140015a38  mov     rcx, [rcx+30h]; HeapHandle
0x140015a3c  call    cs:__imp_RtlFreeHeap
0x140015a42  test    r14, r14
0x140015a45  jz      short loc_140015A5F
0x140015a47  mov     rcx, gs:60h
0x140015a50  mov     r8, r14; P
0x140015a53  xor     edx, edx; Flags
0x140015a55  mov     rcx, [rcx+30h]; HeapHandle
0x140015a59  call    cs:__imp_RtlFreeHeap
0x140015a5f  test    rdi, rdi
0x140015a62  jz      short loc_140015A7C
0x140015a64  mov     rcx, gs:60h
0x140015a6d  mov     r8, rdi; P
0x140015a70  xor     edx, edx; Flags
0x140015a72  mov     rcx, [rcx+30h]; HeapHandle
0x140015a76  call    cs:__imp_RtlFreeHeap
0x140015a7c  mov     rcx, [rbp+KeyHandle]; Handle
0x140015a80  test    rcx, rcx
0x140015a83  jz      short loc_140015A8B
0x140015a85  call    cs:__imp_ZwClose
0x140015a8b  mov     rcx, [rbp+Handle]; Handle
0x140015a8f  test    rcx, rcx
0x140015a92  jz      short loc_140015A9A
0x140015a94  call    cs:__imp_ZwClose
0x140015a9a  mov     eax, ebx
0x140015a9c  mov     rbx, [rsp+40h+arg_0]
0x140015aa4  add     rsp, 40h
0x140015aa8  pop     r15
0x140015aaa  pop     r14
0x140015aac  pop     r13
0x140015aae  pop     r12
0x140015ab0  pop     rdi
0x140015ab1  pop     rsi
0x140015ab2  pop     rbp
0x140015ab3  retn
```
