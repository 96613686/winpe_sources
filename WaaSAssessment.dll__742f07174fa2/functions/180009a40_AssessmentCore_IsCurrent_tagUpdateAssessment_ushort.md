# AssessmentCore::IsCurrent(tagUpdateAssessment &,ushort *)

- ea: `0x180009a40`
- end: `0x180009af8`
- name: `?IsCurrent@AssessmentCore@@MEAAJAEAUtagUpdateAssessment@@PEAG@Z`
- size: `184`
- prototype: `int(AssessmentCore *__hidden this, struct tagUpdateAssessment *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180009a40`
- `0x18001752c`
- `0x180018b8c`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall AssessmentCore::IsCurrent(
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
           (char *)this + 124,
           v8);
    if ( v5 >= 0 )
      return (unsigned int)v5;
LABEL_5:
    LogLevel(2u, (wchar_t *)L"IsCurrent Failure: 0x%x", (unsigned int)v5);
    return (unsigned int)v5;
  }
  LogLevel(4u, (wchar_t *)L"Device is latest");
  a2->status = UpdateAssessmentStatus_Latest;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180009a40  mov     r11, rsp
0x180009a43  mov     [r11+18h], rbx
0x180009a47  mov     [r11+20h], rsi
0x180009a4b  push    rdi
0x180009a4c  sub     rsp, 30h
0x180009a50  mov     rax, r8
0x180009a53  mov     qword ptr [rdx+4], 0
0x180009a5b  mov     rdi, rdx
0x180009a5e  mov     [rsp+38h+arg_0], 0
0x180009a66  lea     rdx, [rcx+6F0h]; unsigned __int16 *
0x180009a6d  mov     [rsp+38h+arg_8], 0
0x180009a75  mov     rsi, rcx
0x180009a78  lea     r9, [r11+10h]; int *
0x180009a7c  mov     rcx, rax; unsigned __int16 *
0x180009a7f  lea     r8, [r11+8]; int *
0x180009a83  call    ?IsOSVersionPresentInList@@YAJPEBG0AEAH1@Z; IsOSVersionPresentInList(ushort const *,ushort const *,int &,int &)
0x180009a88  mov     ebx, eax
0x180009a8a  test    eax, eax
0x180009a8c  js      short loc_180009AD2
0x180009a8e  cmp     [rsp+38h+arg_0], 0
0x180009a93  jz      short loc_180009AAE
0x180009a95  lea     rdx, aDeviceIsLatest; "Device is latest"
0x180009a9c  mov     ecx, 4; unsigned __int8
0x180009aa1  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009aa6  mov     dword ptr [rdi], 0
0x180009aac  jmp     short loc_180009AE6
0x180009aae  mov     rax, [rsi]
0x180009ab1  lea     r8, [rsi+7Ch]
0x180009ab5  mov     r9d, [rsp+38h+arg_8]
0x180009aba  mov     rdx, rdi
0x180009abd  mov     rcx, rsi
0x180009ac0  mov     rax, [rax+0E0h]
0x180009ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009acc  mov     ebx, eax
0x180009ace  test    eax, eax
0x180009ad0  jns     short loc_180009AE6
0x180009ad2  mov     r8d, ebx
0x180009ad5  lea     rdx, aIscurrentFailu; "IsCurrent Failure: 0x%x"
0x180009adc  mov     ecx, 2; unsigned __int8
0x180009ae1  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009ae6  mov     rsi, [rsp+38h+arg_18]
0x180009aeb  mov     eax, ebx
0x180009aed  mov     rbx, [rsp+38h+arg_10]
0x180009af2  add     rsp, 30h
0x180009af6  pop     rdi
0x180009af7  retn
```
