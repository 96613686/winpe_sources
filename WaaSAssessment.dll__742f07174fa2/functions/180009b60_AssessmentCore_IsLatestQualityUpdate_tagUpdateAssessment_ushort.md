# AssessmentCore::IsLatestQualityUpdate(tagUpdateAssessment &,ushort *)

- ea: `0x180009b60`
- end: `0x180009c1b`
- name: `?IsLatestQualityUpdate@AssessmentCore@@MEAAJAEAUtagUpdateAssessment@@PEAG@Z`
- size: `187`
- prototype: `int(AssessmentCore *__hidden this, struct tagUpdateAssessment *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180009b60`
- `0x18001752c`
- `0x180018b8c`
- `0x18001b010`

## string_xrefs

- `0x180009bf8`: `IsLatestQualityUpdate Failure: 0x%x`

## pseudocode

```c
__int64 __fastcall AssessmentCore::IsLatestQualityUpdate(
        AssessmentCore *this,
        struct tagUpdateAssessment *a2,
        unsigned __int16 *a3)
{
  int v5; // ebx
  int v7; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v8; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)&a2->impact = 0;
  v7 = 0;
  v8 = 0;
  v5 = IsOSVersionPresentInList(a3, (unsigned __int16 *)this + 888, &v7, (int *)&v8);
  if ( v5 < 0 )
    goto LABEL_5;
  if ( !v7 )
  {
    v5 = (*(__int64 (__fastcall **)(AssessmentCore *, struct tagUpdateAssessment *, char *, _QWORD))(*(_QWORD *)this + 224LL))(
           this,
           a2,
           (char *)this + 148,
           v8);
    if ( v5 >= 0 )
      return (unsigned int)v5;
LABEL_5:
    LogLevel(2u, L"IsLatestQualityUpdate Failure: 0x%x", (unsigned int)v5);
    return (unsigned int)v5;
  }
  LogLevel(4u, L"Device is latest");
  a2->status = UpdateAssessmentStatus_Latest;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180009b60  mov     r11, rsp
0x180009b63  mov     [r11+18h], rbx
0x180009b67  mov     [r11+20h], rsi
0x180009b6b  push    rdi
0x180009b6c  sub     rsp, 30h
0x180009b70  mov     rax, r8
0x180009b73  mov     qword ptr [rdx+4], 0
0x180009b7b  mov     rdi, rdx
0x180009b7e  mov     [rsp+38h+arg_0], 0
0x180009b86  lea     rdx, [rcx+6F0h]; unsigned __int16 *
0x180009b8d  mov     [rsp+38h+arg_8], 0
0x180009b95  mov     rsi, rcx
0x180009b98  lea     r9, [r11+10h]; int *
0x180009b9c  mov     rcx, rax; unsigned __int16 *
0x180009b9f  lea     r8, [r11+8]; int *
0x180009ba3  call    ?IsOSVersionPresentInList@@YAJPEBG0AEAH1@Z; IsOSVersionPresentInList(ushort const *,ushort const *,int &,int &)
0x180009ba8  mov     ebx, eax
0x180009baa  test    eax, eax
0x180009bac  js      short loc_180009BF5
0x180009bae  cmp     [rsp+38h+arg_0], 0
0x180009bb3  jz      short loc_180009BCE
0x180009bb5  lea     rdx, aDeviceIsLatest; "Device is latest"
0x180009bbc  mov     ecx, 4; unsigned __int8
0x180009bc1  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009bc6  mov     dword ptr [rdi], 0
0x180009bcc  jmp     short loc_180009C09
0x180009bce  mov     rax, [rsi]
0x180009bd1  lea     r8, [rsi+94h]
0x180009bd8  mov     r9d, [rsp+38h+arg_8]
0x180009bdd  mov     rdx, rdi
0x180009be0  mov     rcx, rsi
0x180009be3  mov     rax, [rax+0E0h]
0x180009bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bef  mov     ebx, eax
0x180009bf1  test    eax, eax
0x180009bf3  jns     short loc_180009C09
0x180009bf5  mov     r8d, ebx
0x180009bf8  lea     rdx, aIslatestqualit; "IsLatestQualityUpdate Failure: 0x%x"
0x180009bff  mov     ecx, 2; unsigned __int8
0x180009c04  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009c09  mov     rsi, [rsp+38h+arg_18]
0x180009c0e  mov     eax, ebx
0x180009c10  mov     rbx, [rsp+38h+arg_10]
0x180009c15  add     rsp, 30h
0x180009c19  pop     rdi
0x180009c1a  retn
```
