# ipx::mtf::CMtfSuggestionClient::RepairAndRequest(ushort,IMtfPropertyBag *)

- ea: `0x180019a28`
- end: `0x180019af8`
- name: `?RepairAndRequest@CMtfSuggestionClient@mtf@ipx@@IEAAJGPEAUIMtfPropertyBag@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfSuggestionClient *__hidden this, unsigned __int16, struct IMtfPropertyBag *)`
- caller_count: `22`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180014c90`
- `0x1800150a0`
- `0x180015370`
- `0x180015580`
- `0x180015960`
- `0x180015ce0`
- `0x180015e80`
- `0x180016020`
- `0x180016150`
- `0x180016430`
- `0x180016750`
- `0x1800189d0`
- `0x18001a150`
- `0x18001a450`
- `0x18001a800`
- `0x18001aa70`
- `0x18001ae00`
- `0x18001b040`
- `0x18001c840`
- `0x18001cae0`
- `0x18001cdd4`
- `0x18001cf68`

## callees

- `0x180006074`
- `0x180019a28`
- `0x180019b00`
- `0x18002f010`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::RepairAndRequest(
        ipx::mtf::CMtfSuggestionClient *this,
        unsigned __int16 a2,
        struct IMtfPropertyBag *a3)
{
  unsigned int v4; // ebp
  __int64 result; // rax
  int v7; // ebx
  __int64 v8; // rdx
  int v9; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a2;
  result = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, struct IMtfPropertyBag *))(**((_QWORD **)this + 14) + 40LL))(
             *((_QWORD *)this + 14),
             (char *)this + 48,
             a2,
             a3);
  v7 = result;
  if ( (int)result < 0 && !*((_BYTE *)this + 147) )
  {
    if ( (result & 0x1FFF0000) == 0x7B20000 && (_DWORD)result != -2143288316 )
    {
      v8 = 2300;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)(unsigned int)v7,
        v9);
      return (unsigned int)v7;
    }
    v7 = ipx::mtf::CMtfSuggestionClient::RepairServerConnection(this);
    if ( v7 < 0 )
    {
      v8 = 2304;
      goto LABEL_6;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, struct IMtfPropertyBag *))(**((_QWORD **)this + 14) + 40LL))(
           *((_QWORD *)this + 14),
           (char *)this + 48,
           v4,
           a3);
    if ( v7 < 0 )
    {
      v8 = 2307;
      goto LABEL_6;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180019a28  push    rbx
0x180019a2a  push    rbp
0x180019a2b  push    rsi
0x180019a2c  push    rdi
0x180019a2d  push    r14
0x180019a2f  sub     rsp, 30h
0x180019a33  mov     rdi, rcx
0x180019a36  movzx   ebp, dx
0x180019a39  mov     rcx, [rcx+70h]
0x180019a3d  mov     rsi, r8
0x180019a40  mov     r9, r8
0x180019a43  mov     r8d, ebp
0x180019a46  lea     rdx, [rdi+30h]
0x180019a4a  mov     rax, [rcx]
0x180019a4d  mov     rax, [rax+28h]
0x180019a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a56  mov     ebx, eax
0x180019a58  test    eax, eax
0x180019a5a  jns     loc_180019AED
0x180019a60  cmp     byte ptr [rdi+93h], 0
0x180019a67  jnz     loc_180019AED
0x180019a6d  mov     ecx, eax
0x180019a6f  mov     eax, 1FFF0000h
0x180019a74  and     ecx, eax
0x180019a76  cmp     ecx, 10000h
0x180019a7c  jz      short loc_180019AAF
0x180019a7e  mov     ecx, ebx
0x180019a80  and     ecx, eax
0x180019a82  cmp     ecx, 7B20000h
0x180019a88  jnz     short loc_180019AAF
0x180019a8a  cmp     ebx, 80400404h
0x180019a90  jz      short loc_180019AAF
0x180019a92  mov     edx, 8FCh; void *
0x180019a97  mov     rcx, [rsp+58h]; this
0x180019a9c  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180019aa3  mov     r9d, ebx; char *
0x180019aa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019aab  mov     eax, ebx
0x180019aad  jmp     short loc_180019AED
0x180019aaf  mov     rcx, rdi; this
0x180019ab2  call    ?RepairServerConnection@CMtfSuggestionClient@mtf@ipx@@IEAAJXZ; ipx::mtf::CMtfSuggestionClient::RepairServerConnection(void)
0x180019ab7  mov     ebx, eax
0x180019ab9  test    eax, eax
0x180019abb  jns     short loc_180019AC4
0x180019abd  mov     edx, 900h
0x180019ac2  jmp     short loc_180019A97
0x180019ac4  mov     rcx, [rdi+70h]
0x180019ac8  lea     rdx, [rdi+30h]
0x180019acc  mov     r9, rsi
0x180019acf  mov     r8d, ebp
0x180019ad2  mov     rax, [rcx]
0x180019ad5  mov     rax, [rax+28h]
0x180019ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ade  mov     ebx, eax
0x180019ae0  test    eax, eax
0x180019ae2  jns     short loc_180019AEB
0x180019ae4  mov     edx, 903h
0x180019ae9  jmp     short loc_180019A97
0x180019aeb  xor     eax, eax
0x180019aed  add     rsp, 30h
0x180019af1  pop     r14
0x180019af3  pop     rdi
0x180019af4  pop     rsi
0x180019af5  pop     rbp
0x180019af6  pop     rbx
0x180019af7  retn
```
