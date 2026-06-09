# AssessmentCore::IsUpToDate(tagUpdateAssessment &,ushort *,ushort *)

- ea: `0x180009c30`
- end: `0x180009d34`
- name: `?IsUpToDate@AssessmentCore@@MEAAJAEAUtagUpdateAssessment@@PEAG1@Z`
- size: `260`
- prototype: `int(AssessmentCore *__hidden this, struct tagUpdateAssessment *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180009c30`
- `0x18001752c`
- `0x180018b8c`
- `0x18001b010`

## string_xrefs

- `0x180009c99`: `Checking if the device is already current`

## pseudocode

```c
__int64 __fastcall AssessmentCore::IsUpToDate(
        AssessmentCore *this,
        struct tagUpdateAssessment *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v4; // rbp
  int v8; // ebx
  int v9; // eax
  int v11; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+58h] [rbp+10h] BYREF

  *(_QWORD *)&a2->impact = 0;
  v4 = (unsigned __int16 *)((char *)this + 1776);
  v11 = 0;
  v12 = 0;
  v8 = IsOSVersionPresentInList(a3, (unsigned __int16 *)this + 888, &v11, &v12);
  if ( v8 < 0 )
    goto LABEL_9;
  v9 = v11;
  if ( !v11 )
  {
    if ( !v12 )
    {
      LogLevel(v11 + 4, L"Checking if the device is already current");
      v8 = IsOSVersionPresentInList(a4, v4, &v11, &v12);
      if ( v8 < 0 )
        goto LABEL_9;
      v9 = v11;
    }
    if ( v9 )
      goto LABEL_7;
    v8 = (*(__int64 (__fastcall **)(AssessmentCore *, struct tagUpdateAssessment *, char *, _QWORD))(*(_QWORD *)this + 224LL))(
           this,
           a2,
           (char *)this + 132,
           (unsigned int)v12);
    if ( v8 >= 0 )
      return (unsigned int)v8;
LABEL_9:
    LogLevel(2u, L"IsUpToDate Failure: 0x%x", (unsigned int)v8);
    return (unsigned int)v8;
  }
LABEL_7:
  LogLevel(4u, L"Device is latest");
  a2->status = UpdateAssessmentStatus_Latest;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180009c30  mov     r11, rsp
0x180009c33  mov     [r11+18h], rbx
0x180009c37  mov     [r11+20h], rbp
0x180009c3b  push    rsi
0x180009c3c  push    rdi
0x180009c3d  push    r14
0x180009c3f  sub     rsp, 30h
0x180009c43  mov     rax, r8
0x180009c46  mov     qword ptr [rdx+4], 0
0x180009c4e  lea     rbp, [rcx+6F0h]
0x180009c55  mov     [rsp+48h+arg_0], 0
0x180009c5d  mov     r14, r9
0x180009c60  mov     [rsp+48h+arg_8], 0
0x180009c68  mov     rdi, rdx
0x180009c6b  lea     r9, [r11+10h]; int *
0x180009c6f  mov     rsi, rcx
0x180009c72  lea     r8, [r11+8]; int *
0x180009c76  mov     rdx, rbp; unsigned __int16 *
0x180009c79  mov     rcx, rax; unsigned __int16 *
0x180009c7c  call    ?IsOSVersionPresentInList@@YAJPEBG0AEAH1@Z; IsOSVersionPresentInList(ushort const *,ushort const *,int &,int &)
0x180009c81  mov     ebx, eax
0x180009c83  test    eax, eax
0x180009c85  js      loc_180009D0B
0x180009c8b  mov     eax, [rsp+48h+arg_0]
0x180009c8f  test    eax, eax
0x180009c91  jnz     short loc_180009CCB
0x180009c93  cmp     [rsp+48h+arg_8], eax
0x180009c97  jnz     short loc_180009CC7
0x180009c99  lea     rdx, aCheckingIfTheD; "Checking if the device is already curre"...
0x180009ca0  lea     ecx, [rax+4]; unsigned __int8
0x180009ca3  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009ca8  lea     r9, [rsp+48h+arg_8]; int *
0x180009cad  mov     rdx, rbp; unsigned __int16 *
0x180009cb0  lea     r8, [rsp+48h+arg_0]; int *
0x180009cb5  mov     rcx, r14; unsigned __int16 *
0x180009cb8  call    ?IsOSVersionPresentInList@@YAJPEBG0AEAH1@Z; IsOSVersionPresentInList(ushort const *,ushort const *,int &,int &)
0x180009cbd  mov     ebx, eax
0x180009cbf  test    eax, eax
0x180009cc1  js      short loc_180009D0B
0x180009cc3  mov     eax, [rsp+48h+arg_0]
0x180009cc7  test    eax, eax
0x180009cc9  jz      short loc_180009CE4
0x180009ccb  lea     rdx, aDeviceIsLatest; "Device is latest"
0x180009cd2  mov     ecx, 4; unsigned __int8
0x180009cd7  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009cdc  mov     dword ptr [rdi], 0
0x180009ce2  jmp     short loc_180009D1F
0x180009ce4  mov     rax, [rsi]
0x180009ce7  lea     r8, [rsi+84h]
0x180009cee  mov     r9d, [rsp+48h+arg_8]
0x180009cf3  mov     rdx, rdi
0x180009cf6  mov     rcx, rsi
0x180009cf9  mov     rax, [rax+0E0h]
0x180009d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d05  mov     ebx, eax
0x180009d07  test    eax, eax
0x180009d09  jns     short loc_180009D1F
0x180009d0b  mov     r8d, ebx
0x180009d0e  lea     rdx, aIsuptodateFail; "IsUpToDate Failure: 0x%x"
0x180009d15  mov     ecx, 2; unsigned __int8
0x180009d1a  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009d1f  mov     rbp, [rsp+48h+arg_18]
0x180009d24  mov     eax, ebx
0x180009d26  mov     rbx, [rsp+48h+arg_10]
0x180009d2b  add     rsp, 30h
0x180009d2f  pop     r14
0x180009d31  pop     rdi
0x180009d32  pop     rsi
0x180009d33  retn
```
