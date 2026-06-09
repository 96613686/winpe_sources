# SrppMapFileImage

- ea: `0x14002f05c`
- end: `0x14002f216`
- name: `SrppMapFileImage`
- size: `442`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002ab78`
- `0x14002f434`

## callees

- `0x14002f05c`
- `0x14002f21c`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002f13b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002f13b`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x14002f161`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x14002f161`
- `ntoskrnl!PsInitialSystemProcess` at `0x14002f173`
- `ntoskrnl!MmMapViewOfSection` at `0x14002f1bf`
- `ntoskrnl!MmMapViewOfSection` at `0x14002f1bf`
- `ntoskrnl!ZwCreateSection` at `0x14002f107`
- `ntoskrnl!ZwCreateSection` at `0x14002f107`

## pseudocode

```c
__int64 __fastcall SrppMapFileImage(HANDLE FileHandle, __int64 a2)
{
  __int64 v3; // xmm1_8
  NTSTATUS v4; // ebx
  __int128 v5; // xmm1
  __int64 v6; // xmm0_8
  void *SectionHandle[2]; // [rsp+50h] [rbp-19h] BYREF
  ULONG_PTR ViewSize[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v10; // [rsp+70h] [rbp+7h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp+Fh] BYREF
  PVOID Object; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v13; // [rsp+E0h] [rbp+77h] BYREF

  v10 = 1;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  ViewSize[0] = 0;
  ViewSize[1] = 0;
  v13 = 0;
  *(_OWORD *)SectionHandle = 0;
  if ( FileHandle && a2 )
  {
    v3 = v10;
    *(_OWORD *)a2 = 0;
    ObjectAttributes.Length = 48;
    *(_OWORD *)(a2 + 16) = *(_OWORD *)ViewSize;
    ObjectAttributes.RootDirectory = 0;
    *(_QWORD *)(a2 + 32) = v3;
    ObjectAttributes.Attributes = 512;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.ObjectName = 0;
    v4 = ZwCreateSection(SectionHandle, 5u, &ObjectAttributes, 0, 2u, 0x8000000u, FileHandle);
    if ( v4 >= 0 )
    {
      Object = 0;
      v4 = ObReferenceObjectByHandle(SectionHandle[0], 0, 0, 0, &Object, 0);
      ViewSize[1] = (ULONG_PTR)Object;
      if ( v4 >= 0 )
      {
        v4 = MmMapViewInSystemSpace(Object, &SectionHandle[1], ViewSize);
        if ( v4 >= 0 )
        {
LABEL_8:
          v5 = *(_OWORD *)ViewSize;
          *(_OWORD *)a2 = *(_OWORD *)SectionHandle;
          v6 = v10;
          *(_OWORD *)(a2 + 16) = v5;
          *(_QWORD *)(a2 + 32) = v6;
          return (unsigned int)v4;
        }
        SectionHandle[1] = 0;
        ViewSize[0] = 0;
        v13 = 0;
        v4 = MmMapViewOfSection(ViewSize[1], PsInitialSystemProcess, &SectionHandle[1], 0, 0, &v13, ViewSize, 2, 0, 2);
        if ( v4 >= 0 )
        {
          LOBYTE(v10) = 0;
          goto LABEL_8;
        }
      }
    }
    SrppUnmapFileImage(SectionHandle);
    return (unsigned int)v4;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x14002f05c  mov     [rsp-8+arg_8], rbx
0x14002f061  push    rbp
0x14002f062  push    rsi
0x14002f063  push    rdi
0x14002f064  lea     rbp, [rsp-47h]
0x14002f069  sub     rsp, 0B0h
0x14002f070  xor     esi, esi
0x14002f072  mov     byte ptr [rbp+57h+var_50], 1
0x14002f076  xor     eax, eax
0x14002f078  mov     dword ptr [rbp+57h+ObjectAttributes+4], esi
0x14002f07b  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], esi
0x14002f07e  xorps   xmm0, xmm0
0x14002f081  mov     [rbp+57h+ViewSize], rsi
0x14002f085  mov     rdi, rdx
0x14002f088  mov     [rbp+57h+ViewSize+8], rsi
0x14002f08c  mov     dword ptr [rbp+57h+var_50+1], eax
0x14002f08f  mov     word ptr [rbp+57h+var_50+5], ax
0x14002f093  mov     byte ptr [rbp+57h+var_50+7], al
0x14002f096  mov     [rbp+57h+arg_10], rsi
0x14002f09a  movdqu  xmmword ptr [rbp+57h+SectionHandle], xmm0
0x14002f09f  test    rcx, rcx
0x14002f0a2  jz      loc_14002F1FD
0x14002f0a8  test    rdx, rdx
0x14002f0ab  jz      loc_14002F1FD
0x14002f0b1  movsd   xmm1, [rbp+57h+var_50]
0x14002f0b6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002f0ba  movups  xmmword ptr [rdx], xmm0
0x14002f0bd  mov     [rsp+0C0h+FileHandle], rcx; FileHandle
0x14002f0c2  xor     r9d, r9d; MaximumSize
0x14002f0c5  movups  xmm0, xmmword ptr [rbp+57h+ViewSize]
0x14002f0c9  mov     [rsp+0C0h+AllocationAttributes], 8000000h; AllocationAttributes
0x14002f0d1  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x14002f0d5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002f0dc  movups  xmmword ptr [rdx+10h], xmm0
0x14002f0e0  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x14002f0e4  movsd   qword ptr [rdx+20h], xmm1
0x14002f0e9  xorps   xmm0, xmm0
0x14002f0ec  lea     edx, [rsi+5]; DesiredAccess
0x14002f0ef  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14002f0f6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002f0fb  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x14002f0ff  mov     [rsp+0C0h+SectionPageProtection], 2; SectionPageProtection
0x14002f107  call    cs:__imp_ZwCreateSection
0x14002f10e  nop     dword ptr [rax+rax+00h]
0x14002f113  mov     ebx, eax
0x14002f115  test    eax, eax
0x14002f117  js      loc_14002F1F0
0x14002f11d  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x14002f121  lea     rax, [rbp+57h+Object]
0x14002f125  mov     qword ptr [rsp+0C0h+AllocationAttributes], rsi; HandleInformation
0x14002f12a  xor     r9d, r9d; AccessMode
0x14002f12d  xor     r8d, r8d; ObjectType
0x14002f130  mov     qword ptr [rsp+0C0h+SectionPageProtection], rax; Object
0x14002f135  xor     edx, edx; DesiredAccess
0x14002f137  mov     [rbp+57h+Object], rsi
0x14002f13b  call    cs:__imp_ObReferenceObjectByHandle
0x14002f142  nop     dword ptr [rax+rax+00h]
0x14002f147  mov     rcx, [rbp+57h+Object]; Section
0x14002f14b  mov     ebx, eax
0x14002f14d  mov     [rbp+57h+ViewSize+8], rcx
0x14002f151  test    eax, eax
0x14002f153  js      loc_14002F1F0
0x14002f159  lea     r8, [rbp+57h+ViewSize]; ViewSize
0x14002f15d  lea     rdx, [rbp+57h+SectionHandle+8]; MappedBase
0x14002f161  call    cs:__imp_MmMapViewInSystemSpace
0x14002f168  nop     dword ptr [rax+rax+00h]
0x14002f16d  mov     ebx, eax
0x14002f16f  test    eax, eax
0x14002f171  jns     short loc_14002F1D5
0x14002f173  mov     rdx, cs:__imp_PsInitialSystemProcess
0x14002f17a  lea     rax, [rbp+57h+ViewSize]
0x14002f17e  mov     rcx, [rbp+57h+ViewSize+8]
0x14002f182  lea     r8, [rbp+57h+SectionHandle+8]
0x14002f186  mov     [rsp+0C0h+var_78], 2
0x14002f18e  xor     r9d, r9d
0x14002f191  mov     [rsp+0C0h+var_80], esi
0x14002f195  mov     [rsp+0C0h+var_88], 2
0x14002f19d  mov     [rsp+0C0h+FileHandle], rax
0x14002f1a2  lea     rax, [rbp+57h+arg_10]
0x14002f1a6  mov     [rbp+57h+SectionHandle+8], rsi
0x14002f1aa  mov     [rbp+57h+ViewSize], rsi
0x14002f1ae  mov     [rbp+57h+arg_10], rsi
0x14002f1b2  mov     rdx, [rdx]
0x14002f1b5  mov     qword ptr [rsp+0C0h+AllocationAttributes], rax
0x14002f1ba  mov     qword ptr [rsp+0C0h+SectionPageProtection], rsi
0x14002f1bf  call    cs:__imp_MmMapViewOfSection
0x14002f1c6  nop     dword ptr [rax+rax+00h]
0x14002f1cb  mov     ebx, eax
0x14002f1cd  test    eax, eax
0x14002f1cf  js      short loc_14002F1F0
0x14002f1d1  mov     byte ptr [rbp+57h+var_50], sil
0x14002f1d5  movups  xmm0, xmmword ptr [rbp+57h+SectionHandle]
0x14002f1d9  movups  xmm1, xmmword ptr [rbp+57h+ViewSize]
0x14002f1dd  movups  xmmword ptr [rdi], xmm0
0x14002f1e0  movsd   xmm0, [rbp+57h+var_50]
0x14002f1e5  movups  xmmword ptr [rdi+10h], xmm1
0x14002f1e9  movsd   qword ptr [rdi+20h], xmm0
0x14002f1ee  jmp     short loc_14002F1F9
0x14002f1f0  lea     rcx, [rbp+57h+SectionHandle]
0x14002f1f4  call    SrppUnmapFileImage
0x14002f1f9  mov     eax, ebx
0x14002f1fb  jmp     short loc_14002F202
0x14002f1fd  mov     eax, 0C000000Dh
0x14002f202  mov     rbx, [rsp+0C0h+arg_8]
0x14002f20a  add     rsp, 0B0h
0x14002f211  pop     rdi
0x14002f212  pop     rsi
0x14002f213  pop     rbp
0x14002f214  retn
```
