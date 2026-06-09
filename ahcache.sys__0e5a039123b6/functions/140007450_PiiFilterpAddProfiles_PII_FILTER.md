# PiiFilterpAddProfiles(_PII_FILTER *)

- ea: `0x140007450`
- end: `0x140007673`
- name: `?PiiFilterpAddProfiles@@YAJPEAU_PII_FILTER@@@Z`
- size: `547`
- prototype: `__int64 __fastcall(struct _PII_FILTER *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004158`

## callees

- `0x1400043eb`
- `0x140004469`
- `0x1400044f9`
- `0x140006e18`
- `0x140007394`
- `0x140007450`
- `0x140007e40`
- `0x140031fcc`
- `0x140032048`
- `0x140040564`
- `0x140045d44`
- `0x14005498c`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x140007539`
- `ntoskrnl!ZwEnumerateKey` at `0x140007539`
- `ntoskrnl!_wcslwr` at `0x1400075b3`
- `ntoskrnl!_wcslwr` at `0x1400075b3`

## string_xrefs

- `0x1400074bf`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`
- `0x14000759b`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall PiiFilterpAddProfiles(struct _PII_FILTER *this)
{
  __int64 v2; // rcx
  wchar_t *v3; // rsi
  void *v4; // rdi
  int v5; // ebx
  ULONG i; // r14d
  HANDLE v7; // rcx
  NTSTATUS v8; // eax
  unsigned int j; // ebx
  wchar_t *v10; // rax
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  HANDLE KeyHandle[2]; // [rsp+30h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+88h] [rbp+48h] BYREF
  wchar_t *String; // [rsp+90h] [rbp+50h] BYREF
  HANDLE Handle; // [rsp+98h] [rbp+58h] BYREF

  ResultLength = 0;
  Handle = 0;
  KeyHandle[0] = 0;
  String = 0;
  v3 = (wchar_t *)AslAlloc(this, 536, 1);
  if ( !v3 )
  {
    v4 = 0;
LABEL_3:
    v5 = -1073741801;
    goto LABEL_23;
  }
  v4 = (void *)AslAlloc(v2, 536, 1);
  if ( !v4 )
    goto LABEL_3;
  v5 = AslRegistryOpenKey(
         KeyHandle,
         L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
         8);
  if ( v5 >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      v7 = Handle;
      if ( Handle )
      {
        ZwClose_0(Handle);
        Handle = 0;
      }
      AslFree(v7, String);
      String = 0;
      memset(v4, 0, 0x218u);
      memset(v3, 0, 0x218u);
      v8 = ZwEnumerateKey(KeyHandle[0], i, KeyBasicInformation, v3, 0x217u, &ResultLength);
      if ( v8 == -2147483622 )
        break;
      if ( v8 >= 0 )
      {
        for ( j = 0; j < 3; ++j )
        {
          if ( !wcsicmp_0(v3 + 8, off_14000ACC0[j]) )
            goto LABEL_21;
        }
        if ( (int)AslRegistryOpenSubKey(&Handle) >= 0
          && (int)AslRegistryGetString(&String, Handle, L"ProfileImagePath") >= 0 )
        {
          _wcslwr(String);
          v5 = PiiFilterpAddItemSorted(this, String, L"%USERPROFILE%");
          if ( v5 < 0 )
            goto LABEL_23;
          v10 = wcsrchr_0(String, 0x5Cu);
          if ( v10 )
          {
            if ( v10[1] )
            {
              v5 = RtlNameValueArray::Insert(
                     (struct _PII_FILTER *)((char *)this + 48),
                     v11,
                     v10 + 1,
                     L"%USERNAME%",
                     *((_QWORD *)this + 8));
              if ( v5 < 0 )
                goto LABEL_23;
            }
          }
        }
      }
LABEL_21:
      ;
    }
    v5 = 0;
  }
LABEL_23:
  AslFree(v2, v3);
  AslFree(v12, v4);
  AslFree(v13, String);
  String = 0;
  if ( KeyHandle[0] )
    ZwClose_0(KeyHandle[0]);
  if ( Handle )
    ZwClose_0(Handle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140007450  mov     [rsp-38h+arg_0], rbx
0x140007455  push    rbp
0x140007456  push    rsi
0x140007457  push    rdi
0x140007458  push    r12
0x14000745a  push    r13
0x14000745c  push    r14
0x14000745e  push    r15
0x140007460  mov     rbp, rsp
0x140007463  sub     rsp, 40h
0x140007467  xor     r12d, r12d
0x14000746a  mov     edx, 218h
0x14000746f  mov     r13, rcx
0x140007472  mov     [rbp+arg_8], r12d
0x140007476  mov     [rbp+Handle], r12
0x14000747a  mov     [rbp+KeyHandle], r12
0x14000747e  lea     ebx, [r12+1]
0x140007483  mov     [rbp+String], r12
0x140007487  mov     r8d, ebx
0x14000748a  call    AslAlloc
0x14000748f  mov     rsi, rax
0x140007492  test    rax, rax
0x140007495  jnz     short loc_1400074A4
0x140007497  mov     edi, r12d
0x14000749a  mov     ebx, 0C0000017h
0x14000749f  jmp     loc_14000761F
0x1400074a4  mov     r8d, ebx
0x1400074a7  mov     edx, 218h
0x1400074ac  call    AslAlloc
0x1400074b1  mov     rdi, rax
0x1400074b4  test    rax, rax
0x1400074b7  jz      short loc_14000749A
0x1400074b9  mov     r8d, 8
0x1400074bf  lea     rdx, aRegistryMachin_2; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x1400074c6  lea     rcx, [rbp+KeyHandle]
0x1400074ca  call    AslRegistryOpenKey
0x1400074cf  mov     ebx, eax
0x1400074d1  test    eax, eax
0x1400074d3  js      loc_14000761F
0x1400074d9  mov     r14d, r12d
0x1400074dc  mov     rcx, [rbp+Handle]; Handle
0x1400074e0  test    rcx, rcx
0x1400074e3  jz      short loc_1400074EE
0x1400074e5  call    ZwClose_0
0x1400074ea  mov     [rbp+Handle], r12
0x1400074ee  mov     rdx, [rbp+String]
0x1400074f2  call    AslFree
0x1400074f7  xor     edx, edx; Val
0x1400074f9  mov     [rbp+String], r12
0x1400074fd  mov     r8d, 218h; Size
0x140007503  mov     rcx, rdi; void *
0x140007506  call    memset
0x14000750b  xor     edx, edx; Val
0x14000750d  mov     r8d, 218h; Size
0x140007513  mov     rcx, rsi; void *
0x140007516  call    memset
0x14000751b  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000751f  lea     rax, [rbp+arg_8]
0x140007523  mov     [rsp+40h+ResultLength], rax; ResultLength
0x140007528  mov     r9, rsi; KeyInformation
0x14000752b  xor     r8d, r8d; KeyInformationClass
0x14000752e  mov     [rsp+40h+Length], 217h; Length
0x140007536  mov     edx, r14d; Index
0x140007539  call    cs:__imp_ZwEnumerateKey
0x140007540  nop     dword ptr [rax+rax+00h]
0x140007545  cmp     eax, 8000001Ah
0x14000754a  jz      loc_14000761C
0x140007550  test    eax, eax
0x140007552  js      loc_140007614
0x140007558  mov     ebx, r12d
0x14000755b  cmp     ebx, 3
0x14000755e  jnb     short loc_140007582
0x140007560  lea     rax, off_14000ACC0; "s-1-5-18"
0x140007567  mov     edx, ebx
0x140007569  lea     rcx, [rsi+10h]; Str1
0x14000756d  mov     rdx, [rax+rdx*8]; Str2
0x140007571  call    _wcsicmp_0
0x140007576  test    eax, eax
0x140007578  jz      loc_140007614
0x14000757e  inc     ebx
0x140007580  jmp     short loc_14000755B
0x140007582  mov     rdx, [rbp+KeyHandle]
0x140007586  lea     r8, [rsi+10h]
0x14000758a  lea     rcx, [rbp+Handle]; KeyHandle
0x14000758e  call    AslRegistryOpenSubKey
0x140007593  test    eax, eax
0x140007595  js      short loc_140007614
0x140007597  mov     rdx, [rbp+Handle]
0x14000759b  lea     r8, aProfileimagepa; "ProfileImagePath"
0x1400075a2  lea     rcx, [rbp+String]
0x1400075a6  call    AslRegistryGetString
0x1400075ab  test    eax, eax
0x1400075ad  js      short loc_140007614
0x1400075af  mov     rcx, [rbp+String]; String
0x1400075b3  call    cs:__imp__wcslwr
0x1400075ba  nop     dword ptr [rax+rax+00h]
0x1400075bf  mov     rdx, [rbp+String]; unsigned __int16 *
0x1400075c3  lea     r8, aUserprofile; "%USERPROFILE%"
0x1400075ca  mov     rcx, r13; this
0x1400075cd  call    ?PiiFilterpAddItemSorted@@YAJPEAU_PII_FILTER@@PEBG1@Z; PiiFilterpAddItemSorted(_PII_FILTER *,ushort const *,ushort const *)
0x1400075d2  mov     ebx, eax
0x1400075d4  test    eax, eax
0x1400075d6  js      short loc_14000761F
0x1400075d8  mov     rcx, [rbp+String]; Str
0x1400075dc  mov     edx, 5Ch ; '\'; Ch
0x1400075e1  call    wcsrchr_0
0x1400075e6  test    rax, rax
0x1400075e9  jz      short loc_140007614
0x1400075eb  lea     r8, [rax+2]; unsigned __int16 *
0x1400075ef  cmp     [r8], r12w
0x1400075f3  jz      short loc_140007614
0x1400075f5  lea     rcx, [r13+30h]; this
0x1400075f9  mov     rax, [rcx+10h]
0x1400075fd  lea     r9, aUsername; "%USERNAME%"
0x140007604  mov     qword ptr [rsp+40h+Length], rax; unsigned __int64
0x140007609  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x14000760e  mov     ebx, eax
0x140007610  test    eax, eax
0x140007612  js      short loc_14000761F
0x140007614  inc     r14d
0x140007617  jmp     loc_1400074DC
0x14000761c  mov     ebx, r12d
0x14000761f  mov     rdx, rsi
0x140007622  call    AslFree
0x140007627  mov     rdx, rdi
0x14000762a  call    AslFree
0x14000762f  mov     rdx, [rbp+String]
0x140007633  call    AslFree
0x140007638  mov     rcx, [rbp+KeyHandle]; Handle
0x14000763c  mov     [rbp+String], r12
0x140007640  test    rcx, rcx
0x140007643  jz      short loc_14000764A
0x140007645  call    ZwClose_0
0x14000764a  mov     rcx, [rbp+Handle]; Handle
0x14000764e  test    rcx, rcx
0x140007651  jz      short loc_140007658
0x140007653  call    ZwClose_0
0x140007658  mov     eax, ebx
0x14000765a  mov     rbx, [rsp+40h+arg_0]
0x140007662  add     rsp, 40h
0x140007666  pop     r15
0x140007668  pop     r14
0x14000766a  pop     r13
0x14000766c  pop     r12
0x14000766e  pop     rdi
0x14000766f  pop     rsi
0x140007670  pop     rbp
0x140007671  retn
```
