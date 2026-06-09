# AslRegistryGetString

- ea: `0x140040564`
- end: `0x140040728`
- name: `AslRegistryGetString`
- size: `452`
- prototype: `__int64 __fastcall(_QWORD *, void *, const WCHAR *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140007450`
- `0x140031de4`
- `0x140041638`
- `0x1400479a8`

## callees

- `0x14000436d`
- `0x14000440f`
- `0x14000449f`
- `0x140004553`
- `0x14003e364`
- `0x14003e76c`
- `0x140040564`

## string_xrefs

- `0x14004067d`: `AslRegistryGetString`
- `0x1400406a8`: `AslRegistryGetString`
- `0x1400406da`: `AslRegistryGetString`
- `0x14004070e`: `AslRegistryGetString`

## pseudocode

```c
__int64 __fastcall AslRegistryGetString(_QWORD *a1, void *a2, const WCHAR *a3)
{
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  _DWORD *Pool2_0; // rax
  _DWORD *v8; // rdi
  NTSTATUS v9; // eax
  const char *v11; // r9
  __int64 v12; // r8
  __int64 Length; // [rsp+20h] [rbp-48h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp+8h] BYREF

  *a1 = 0;
  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString_0(&DestinationString, a3);
  v5 = ZwQueryValueKey_0(a2, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
  v6 = v5;
  if ( v5 != -1073741772 )
  {
    if ( v5 != -2147483643 && v5 != -1073741789 )
    {
      AslLogCallPrintf(1, "AslRegistryGetString", 1334, "Failed to query key value [%x]", v5);
      return v6;
    }
    ResultLength += 2;
    Pool2_0 = (_DWORD *)ExAllocatePool2_0(256, ResultLength, 1953517633);
    v8 = Pool2_0;
    if ( !Pool2_0 )
    {
      v6 = -1073741801;
      AslLogCallPrintf(1, "AslRegistryGetString", 1348, "Out of memory");
      return v6;
    }
    v9 = ZwQueryValueKey_0(a2, &DestinationString, KeyValuePartialInformation, Pool2_0, ResultLength, &ResultLength);
    v6 = v9;
    if ( v9 < 0 )
    {
      v11 = "Failed to query key value [%x]";
      v12 = 1360;
    }
    else
    {
      if ( (unsigned int)(v8[1] - 1) > 1 )
      {
        AslLogCallPrintf(1, "AslRegistryGetString", 1368, "Invalid value type");
        v6 = -1073741788;
        goto LABEL_7;
      }
      *((_WORD *)v8 + ((unsigned __int64)(unsigned int)v8[2] >> 1) + 6) = 0;
      v9 = AslStringDuplicate(a1, v8 + 3);
      v6 = v9;
      if ( v9 >= 0 )
      {
LABEL_7:
        ExFreePoolWithTag_0(v8, 0x74705041u);
        return v6;
      }
      v11 = "Out of memory [%x]";
      v12 = 1378;
    }
    LODWORD(Length) = v9;
    AslLogCallPrintf(1, "AslRegistryGetString", v12, v11, Length);
    goto LABEL_7;
  }
  return v6;
}

```

## disassembly

```asm
0x140040564  push    rbx
0x140040566  push    rsi
0x140040567  push    rdi
0x140040568  push    r14
0x14004056a  sub     rsp, 48h
0x14004056e  mov     rsi, rdx
0x140040571  mov     qword ptr [rcx], 0
0x140040578  mov     r14, rcx
0x14004057b  mov     [rsp+68h+arg_0], 0
0x140040583  xorps   xmm0, xmm0
0x140040586  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14004058b  mov     rdx, r8; SourceString
0x14004058e  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140040593  call    RtlInitUnicodeString_0
0x140040598  xor     r9d, r9d; KeyValueInformation
0x14004059b  lea     rax, [rsp+68h+arg_0]
0x1400405a0  mov     [rsp+68h+ResultLength], rax; ResultLength
0x1400405a5  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x1400405aa  mov     rcx, rsi; KeyHandle
0x1400405ad  mov     dword ptr [rsp+68h+Length], 0; Length
0x1400405b5  lea     r8d, [r9+2]; KeyValueInformationClass
0x1400405b9  call    ZwQueryValueKey_0
0x1400405be  mov     ebx, eax
0x1400405c0  cmp     eax, 0C0000034h
0x1400405c5  jz      loc_14004068E
0x1400405cb  cmp     eax, 80000005h
0x1400405d0  jnz     loc_1400406C0
0x1400405d6  mov     eax, [rsp+68h+arg_0]
0x1400405da  mov     ecx, 100h
0x1400405df  add     eax, 2
0x1400405e2  mov     r8d, 74705041h
0x1400405e8  mov     edx, eax
0x1400405ea  mov     [rsp+68h+arg_0], eax
0x1400405ee  call    ExAllocatePool2_0
0x1400405f3  mov     rdi, rax
0x1400405f6  test    rax, rax
0x1400405f9  jz      loc_1400406CD
0x1400405ff  lea     rax, [rsp+68h+arg_0]
0x140040604  mov     r9, rdi; KeyValueInformation
0x140040607  mov     [rsp+68h+ResultLength], rax; ResultLength
0x14004060c  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x140040611  mov     eax, [rsp+68h+arg_0]
0x140040615  mov     r8d, 2; KeyValueInformationClass
0x14004061b  mov     rcx, rsi; KeyHandle
0x14004061e  mov     dword ptr [rsp+68h+Length], eax; Length
0x140040622  call    ZwQueryValueKey_0
0x140040627  mov     ebx, eax
0x140040629  test    eax, eax
0x14004062b  js      loc_1400406F2
0x140040631  mov     eax, [rdi+4]
0x140040634  dec     eax
0x140040636  cmp     eax, 1
0x140040639  ja      short loc_14004069B
0x14004063b  mov     ecx, [rdi+8]
0x14004063e  lea     rdx, [rdi+0Ch]
0x140040642  shr     rcx, 1
0x140040645  xor     eax, eax
0x140040647  mov     [rdx+rcx*2], ax
0x14004064b  mov     rcx, r14
0x14004064e  call    AslStringDuplicate
0x140040653  mov     ebx, eax
0x140040655  test    eax, eax
0x140040657  js      loc_140040701
0x14004065d  mov     edx, 74705041h; Tag
0x140040662  mov     rcx, rdi; P
0x140040665  call    ExFreePoolWithTag_0
0x14004066a  jmp     short loc_14004068E
0x14004066c  lea     r9, aFailedToQueryK_0; "Failed to query key value [%x]"
0x140040673  mov     dword ptr [rsp+68h+Length], eax
0x140040677  mov     r8d, 536h
0x14004067d  lea     rdx, aAslregistryget_2; "AslRegistryGetString"
0x140040684  mov     ecx, 1
0x140040689  call    AslLogCallPrintf
0x14004068e  mov     eax, ebx
0x140040690  add     rsp, 48h
0x140040694  pop     r14
0x140040696  pop     rdi
0x140040697  pop     rsi
0x140040698  pop     rbx
0x140040699  retn
0x14004069b  lea     r9, aInvalidValueTy; "Invalid value type"
0x1400406a2  mov     r8d, 558h
0x1400406a8  lea     rdx, aAslregistryget_2; "AslRegistryGetString"
0x1400406af  mov     ecx, 1
0x1400406b4  call    AslLogCallPrintf
0x1400406b9  mov     ebx, 0C0000024h
0x1400406be  jmp     short loc_14004065D
0x1400406c0  cmp     eax, 0C0000023h
0x1400406c5  jz      loc_1400405D6
0x1400406cb  jmp     short loc_14004066C
0x1400406cd  lea     r9, aOutOfMemory; "Out of memory"
0x1400406d4  mov     r8d, 544h
0x1400406da  lea     rdx, aAslregistryget_2; "AslRegistryGetString"
0x1400406e1  mov     ecx, 1
0x1400406e6  mov     ebx, 0C0000017h
0x1400406eb  call    AslLogCallPrintf
0x1400406f0  jmp     short loc_14004068E
0x1400406f2  lea     r9, aFailedToQueryK_0; "Failed to query key value [%x]"
0x1400406f9  mov     r8d, 550h
0x1400406ff  jmp     short loc_14004070E
0x140040701  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x140040708  mov     r8d, 562h
0x14004070e  lea     rdx, aAslregistryget_2; "AslRegistryGetString"
0x140040715  mov     dword ptr [rsp+68h+Length], eax
0x140040719  mov     ecx, 1
0x14004071e  call    AslLogCallPrintf
0x140040723  jmp     loc_14004065D
```
