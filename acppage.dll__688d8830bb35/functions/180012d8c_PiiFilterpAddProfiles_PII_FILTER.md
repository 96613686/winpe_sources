# PiiFilterpAddProfiles(_PII_FILTER *)

- ea: `0x180012d8c`
- end: `0x180013015`
- name: `?PiiFilterpAddProfiles@@YAJPEAU_PII_FILTER@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(struct _PII_FILTER *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ffcc`

## callees

- `0x180001f66`
- `0x180012a24`
- `0x180012ce8`
- `0x180012d8c`
- `0x18001551c`
- `0x18001590c`
- `0x1800159a4`
- `0x18001623a`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180012f47`
- `msvcrt!wcsrchr` at `0x180012f47`
- `msvcrt!_wcslwr` at `0x180012f22`
- `msvcrt!_wcslwr` at `0x180012f22`
- `ntdll!ZwClose` at `0x180012e3f`
- `ntdll!ZwClose` at `0x180012fe6`
- `ntdll!ZwClose` at `0x180012ff5`
- `ntdll!ZwClose` at `0x180012e3f`
- `ntdll!ZwClose` at `0x180012fe6`
- `ntdll!ZwClose` at `0x180012ff5`
- `ntdll!ZwEnumerateKey` at `0x180012eaa`
- `ntdll!ZwEnumerateKey` at `0x180012eaa`
- `ntdll!RtlFreeHeap` at `0x180012e60`
- `ntdll!RtlFreeHeap` at `0x180012f9d`
- `ntdll!RtlFreeHeap` at `0x180012fba`
- `ntdll!RtlFreeHeap` at `0x180012fd7`
- `ntdll!RtlFreeHeap` at `0x180012e60`
- `ntdll!RtlFreeHeap` at `0x180012f9d`
- `ntdll!RtlFreeHeap` at `0x180012fba`
- `ntdll!RtlFreeHeap` at `0x180012fd7`
- `ntdll!RtlAllocateHeap` at `0x180012dd4`
- `ntdll!RtlAllocateHeap` at `0x180012dfe`
- `ntdll!RtlAllocateHeap` at `0x180012dd4`
- `ntdll!RtlAllocateHeap` at `0x180012dfe`

## string_xrefs

- `0x180012f07`: `ProfileImagePath`
- `0x180012e19`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`

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
            while ( wcsicmp_0(Heap + 8, off_180018860[v8]) )
            {
              if ( (unsigned int)++v8 >= 3 )
              {
                if ( AslRegistryOpenSubKey(&Handle, KeyHandle, Heap + 8) >= 0 )
                {
                  v9 = AslRegistryGetString(&String, Handle, L"ProfileImagePath");
                  v2 = String;
                  if ( v9 >= 0 )
                  {
                    _wcslwr(String);
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
0x180012d8c  mov     [rsp-38h+arg_0], rbx
0x180012d91  push    rbp
0x180012d92  push    rsi
0x180012d93  push    rdi
0x180012d94  push    r12
0x180012d96  push    r13
0x180012d98  push    r14
0x180012d9a  push    r15
0x180012d9c  mov     rbp, rsp
0x180012d9f  sub     rsp, 40h
0x180012da3  xor     r15d, r15d
0x180012da6  mov     r13, rcx
0x180012da9  mov     [rbp+arg_8], r15d
0x180012dad  mov     r14d, 218h
0x180012db3  mov     [rbp+Handle], r15
0x180012db7  mov     r8d, r14d; Size
0x180012dba  mov     [rbp+KeyHandle], r15
0x180012dbe  mov     edi, r15d
0x180012dc1  mov     rcx, gs:60h
0x180012dca  lea     ebx, [r15+8]
0x180012dce  mov     edx, ebx; Flags
0x180012dd0  mov     rcx, [rcx+30h]; HeapHandle
0x180012dd4  call    cs:__imp_RtlAllocateHeap
0x180012dda  mov     rsi, rax
0x180012ddd  test    rax, rax
0x180012de0  jnz     short loc_180012DEC
0x180012de2  mov     ebx, 0C0000017h
0x180012de7  jmp     loc_180012FC0
0x180012dec  mov     rcx, gs:60h
0x180012df5  mov     r8, r14; Size
0x180012df8  mov     edx, ebx; Flags
0x180012dfa  mov     rcx, [rcx+30h]; HeapHandle
0x180012dfe  call    cs:__imp_RtlAllocateHeap
0x180012e04  mov     r14, rax
0x180012e07  test    rax, rax
0x180012e0a  jnz     short loc_180012E16
0x180012e0c  mov     ebx, 0C0000017h
0x180012e11  jmp     loc_180012F8B
0x180012e16  mov     r8d, ebx
0x180012e19  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x180012e20  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180012e24  call    AslRegistryOpenKey
0x180012e29  mov     ebx, eax
0x180012e2b  test    eax, eax
0x180012e2d  js      loc_180012F8B
0x180012e33  mov     r12d, r15d
0x180012e36  mov     rcx, [rbp+Handle]; Handle
0x180012e3a  test    rcx, rcx
0x180012e3d  jz      short loc_180012E49
0x180012e3f  call    cs:__imp_ZwClose
0x180012e45  mov     [rbp+Handle], r15
0x180012e49  test    rdi, rdi
0x180012e4c  jz      short loc_180012E66
0x180012e4e  mov     rcx, gs:60h
0x180012e57  mov     r8, rdi; P
0x180012e5a  xor     edx, edx; Flags
0x180012e5c  mov     rcx, [rcx+30h]; HeapHandle
0x180012e60  call    cs:__imp_RtlFreeHeap
0x180012e66  mov     ebx, 218h
0x180012e6b  mov     [rbp+String], r15
0x180012e6f  mov     r8d, ebx; Size
0x180012e72  xor     edx, edx; Val
0x180012e74  mov     rcx, r14; void *
0x180012e77  mov     rdi, r15
0x180012e7a  call    memset_0
0x180012e7f  mov     r8d, ebx; Size
0x180012e82  xor     edx, edx; Val
0x180012e84  mov     rcx, rsi; void *
0x180012e87  call    memset_0
0x180012e8c  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180012e90  lea     rax, [rbp+arg_8]
0x180012e94  mov     [rsp+40h+ResultLength], rax; ResultLength
0x180012e99  mov     r9, rsi; KeyInformation
0x180012e9c  xor     r8d, r8d; KeyInformationClass
0x180012e9f  mov     [rsp+40h+Length], 217h; Length
0x180012ea7  mov     edx, r12d; Index
0x180012eaa  call    cs:__imp_ZwEnumerateKey
0x180012eb0  cmp     eax, 8000001Ah
0x180012eb5  jz      loc_180012F88
0x180012ebb  test    eax, eax
0x180012ebd  js      loc_180012F80
0x180012ec3  mov     ebx, r15d
0x180012ec6  lea     rax, off_180018860; "s-1-5-18"
0x180012ecd  mov     edx, ebx
0x180012ecf  lea     rcx, [rsi+10h]; String1
0x180012ed3  mov     rdx, [rax+rdx*8]; String2
0x180012ed7  call    _wcsicmp_0
0x180012edc  test    eax, eax
0x180012ede  jz      loc_180012F7D
0x180012ee4  inc     ebx
0x180012ee6  cmp     ebx, 3
0x180012ee9  jb      short loc_180012EC6
0x180012eeb  mov     rdx, [rbp+KeyHandle]
0x180012eef  lea     r8, [rsi+10h]
0x180012ef3  lea     rcx, [rbp+Handle]; KeyHandle
0x180012ef7  call    AslRegistryOpenSubKey
0x180012efc  xor     r15d, r15d
0x180012eff  test    eax, eax
0x180012f01  js      short loc_180012F80
0x180012f03  mov     rdx, [rbp+Handle]
0x180012f07  lea     r8, aProfileimagepa; "ProfileImagePath"
0x180012f0e  lea     rcx, [rbp+String]
0x180012f12  call    AslRegistryGetString
0x180012f17  mov     rdi, [rbp+String]
0x180012f1b  test    eax, eax
0x180012f1d  js      short loc_180012F80
0x180012f1f  mov     rcx, rdi; String
0x180012f22  call    cs:__imp__wcslwr
0x180012f28  lea     r8, aUserprofile; "%USERPROFILE%"
0x180012f2f  mov     rdx, rdi; unsigned __int16 *
0x180012f32  mov     rcx, r13; this
0x180012f35  call    ?PiiFilterpAddItemSorted@@YAJPEAU_PII_FILTER@@PEBG1@Z; PiiFilterpAddItemSorted(_PII_FILTER *,ushort const *,ushort const *)
0x180012f3a  mov     ebx, eax
0x180012f3c  test    eax, eax
0x180012f3e  js      short loc_180012F8B
0x180012f40  lea     edx, [r15+5Ch]; Ch
0x180012f44  mov     rcx, rdi; Str
0x180012f47  call    cs:__imp_wcsrchr
0x180012f4d  test    rax, rax
0x180012f50  jz      short loc_180012F80
0x180012f52  lea     r8, [rax+2]; unsigned __int16 *
0x180012f56  cmp     [r8], r15w
0x180012f5a  jz      short loc_180012F80
0x180012f5c  lea     rcx, [r13+30h]; this
0x180012f60  mov     rax, [rcx+10h]
0x180012f64  lea     r9, aUsername; "%USERNAME%"
0x180012f6b  mov     qword ptr [rsp+40h+Length], rax; unsigned __int64
0x180012f70  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x180012f75  mov     ebx, eax
0x180012f77  test    eax, eax
0x180012f79  js      short loc_180012F8B
0x180012f7b  jmp     short loc_180012F80
0x180012f7d  xor     r15d, r15d
0x180012f80  inc     r12d
0x180012f83  jmp     loc_180012E36
0x180012f88  mov     ebx, r15d
0x180012f8b  mov     rcx, gs:60h
0x180012f94  mov     r8, rsi; P
0x180012f97  xor     edx, edx; Flags
0x180012f99  mov     rcx, [rcx+30h]; HeapHandle
0x180012f9d  call    cs:__imp_RtlFreeHeap
0x180012fa3  test    r14, r14
0x180012fa6  jz      short loc_180012FC0
0x180012fa8  mov     rcx, gs:60h
0x180012fb1  mov     r8, r14; P
0x180012fb4  xor     edx, edx; Flags
0x180012fb6  mov     rcx, [rcx+30h]; HeapHandle
0x180012fba  call    cs:__imp_RtlFreeHeap
0x180012fc0  test    rdi, rdi
0x180012fc3  jz      short loc_180012FDD
0x180012fc5  mov     rcx, gs:60h
0x180012fce  mov     r8, rdi; P
0x180012fd1  xor     edx, edx; Flags
0x180012fd3  mov     rcx, [rcx+30h]; HeapHandle
0x180012fd7  call    cs:__imp_RtlFreeHeap
0x180012fdd  mov     rcx, [rbp+KeyHandle]; Handle
0x180012fe1  test    rcx, rcx
0x180012fe4  jz      short loc_180012FEC
0x180012fe6  call    cs:__imp_ZwClose
0x180012fec  mov     rcx, [rbp+Handle]; Handle
0x180012ff0  test    rcx, rcx
0x180012ff3  jz      short loc_180012FFB
0x180012ff5  call    cs:__imp_ZwClose
0x180012ffb  mov     eax, ebx
0x180012ffd  mov     rbx, [rsp+40h+arg_0]
0x180013005  add     rsp, 40h
0x180013009  pop     r15
0x18001300b  pop     r14
0x18001300d  pop     r13
0x18001300f  pop     r12
0x180013011  pop     rdi
0x180013012  pop     rsi
0x180013013  pop     rbp
0x180013014  retn
```
