# ChangeApplicationServices::QueryInterface(_GUID const &,void * *)

- ea: `0x1800260c0`
- end: `0x1800261c2`
- name: `?QueryInterface@ChangeApplicationServices@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180048990`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x1800260c0`
- `0x180094010`

## string_xrefs

- `0x1800260f5`: `ChangeApplicationServices::QueryInterface`
- `0x18002619b`: `ChangeApplicationServices::QueryInterface`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::QueryInterface(
        ChangeApplicationServices *this,
        const struct _GUID *a2,
        void **a3)
{
  PVOID *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rax

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::QueryInterface");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( !v8 )
      goto LABEL_14;
    v9 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IChangeApplicationServices.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IChangeApplicationServices.Data1 )
      v9 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IChangeApplicationServices.Data4;
    if ( v9 )
    {
      this = 0;
    }
    else
    {
LABEL_14:
      if ( this )
      {
        *a3 = this;
        (*(void (__fastcall **)(ChangeApplicationServices *))(*(_QWORD *)this + 8LL))(this);
        v7 = 0;
        goto LABEL_17;
      }
    }
    v7 = -2147467262;
    *a3 = this;
LABEL_17:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v7 = -2147467261;
LABEL_18:
  if ( v6 != &WPP_GLOBAL_Control && *((char *)v6 + 28) < 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      11,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::QueryInterface",
      v7);
  return v7;
}

```

## disassembly

```asm
0x1800260c0  push    rbx
0x1800260c2  push    rbp
0x1800260c3  push    rsi
0x1800260c4  push    rdi
0x1800260c5  sub     rsp, 38h
0x1800260c9  mov     rsi, r8
0x1800260cc  mov     rbx, rdx
0x1800260cf  mov     rdi, rcx
0x1800260d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800260d9  lea     rbp, WPP_GLOBAL_Control
0x1800260e0  cmp     rcx, rbp
0x1800260e3  jz      short loc_180026114
0x1800260e5  test    byte ptr [rcx+1Ch], 80h
0x1800260e9  jz      short loc_180026114
0x1800260eb  cmp     byte ptr [rcx+19h], 5
0x1800260ef  jb      short loc_180026114
0x1800260f1  mov     rcx, [rcx+10h]
0x1800260f5  lea     r9, aChangeapplicat_36; "ChangeApplicationServices::QueryInterfa"...
0x1800260fc  mov     edx, 0Ah
0x180026101  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180026108  call    WPP_SF_s
0x18002610d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026114  test    rsi, rsi
0x180026117  jnz     short loc_180026120
0x180026119  mov     ebx, 80004003h
0x18002611e  jmp     short loc_180026186
0x180026120  mov     rax, [rbx]
0x180026123  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18002612a  jnz     short loc_180026137
0x18002612c  mov     rax, [rbx+8]
0x180026130  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180026137  test    rax, rax
0x18002613a  jz      short loc_18002615C
0x18002613c  mov     rax, [rbx]
0x18002613f  sub     rax, qword ptr cs:IID_IChangeApplicationServices.Data1
0x180026146  jnz     short loc_180026153
0x180026148  mov     rax, [rbx+8]
0x18002614c  sub     rax, qword ptr cs:IID_IChangeApplicationServices.Data4
0x180026153  test    rax, rax
0x180026156  jz      short loc_18002615C
0x180026158  xor     edi, edi
0x18002615a  jmp     short loc_180026161
0x18002615c  test    rdi, rdi
0x18002615f  jnz     short loc_18002616B
0x180026161  mov     ebx, 80004002h
0x180026166  mov     [rsi], rdi
0x180026169  jmp     short loc_18002617F
0x18002616b  mov     [rsi], rdi
0x18002616e  mov     rcx, rdi
0x180026171  mov     rax, [rdi]
0x180026174  mov     rax, [rax+8]
0x180026178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002617d  xor     ebx, ebx
0x18002617f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026186  cmp     rcx, rbp
0x180026189  jz      short loc_1800261B7
0x18002618b  test    byte ptr [rcx+1Ch], 80h
0x18002618f  jz      short loc_1800261B7
0x180026191  cmp     byte ptr [rcx+19h], 5
0x180026195  jb      short loc_1800261B7
0x180026197  mov     rcx, [rcx+10h]
0x18002619b  lea     r9, aChangeapplicat_36; "ChangeApplicationServices::QueryInterfa"...
0x1800261a2  mov     edx, 0Bh
0x1800261a7  mov     [rsp+58h+var_38], ebx
0x1800261ab  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x1800261b2  call    WPP_SF_sD
0x1800261b7  mov     eax, ebx
0x1800261b9  add     rsp, 38h
0x1800261bd  pop     rdi
0x1800261be  pop     rsi
0x1800261bf  pop     rbp
0x1800261c0  pop     rbx
0x1800261c1  retn
```
