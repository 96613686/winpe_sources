# sub_1800BBD7C

- ea: `0x1800bbd7c`
- end: `0x1800bc021`
- name: `sub_1800BBD7C`
- size: `677`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18009bb50`

## callees

- `0x180090894`
- `0x1800916f8`
- `0x180098d54`
- `0x180098e08`
- `0x1800ace5c`
- `0x1800ad3b4`
- `0x1800ad474`
- `0x1800bbd7c`
- `0x1800c87ac`
- `0x1800c9220`
- `0x1800ca1a4`
- `0x1800ca7e8`
- `0x1800cab30`
- `0x1801d6c50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800bbfd7`
- `KERNEL32!GetLastError` at `0x1800bbfd7`
- `KERNEL32!DeleteFileW` at `0x1800bbfcd`
- `KERNEL32!DeleteFileW` at `0x1800bbfcd`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800bbdba`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800bbe3b`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800bbea9`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800bbdba`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800bbe3b`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1800bbea9`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800bbee1`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800bbf63`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800bbf7f`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800bbee1`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800bbf63`
- `Mso20Win32Client!Mso20Win32Client_53248` at `0x1800bbf7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall sub_1800BBD7C(_QWORD *a1, const wchar_t *a2, int a3, int a4, int a5, __int64 a6, _BYTE *a7)
{
  __int64 v10; // rsi
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // r14
  int v15; // r12d
  __int64 v16; // rax
  int v17; // r9d
  __int64 v18; // rax
  bool v19; // zf
  unsigned int v20; // r15d
  DWORD LastError; // eax
  __int64 v22; // rcx
  _QWORD v24[2]; // [rsp+48h] [rbp-38h] BYREF
  _DWORD v25[10]; // [rsp+58h] [rbp-28h] BYREF

  v10 = 0;
  v11 = 0;
  v12 = Mso20Win32Client_52497(1328, 2);
  v24[1] = v12;
  if ( v12 )
    v14 = sub_180090894(v12, *a1, a7);
  else
    v14 = 0;
  if ( !v14 )
    sub_180098E08(a7, 4294966285LL);
  if ( (*a7 & 8) != 0 || (sub_1800916F8(v14, a1[31], a2, a3, a4, a5, a6, a7), (*a7 & 8) != 0) )
  {
    v15 = 0;
  }
  else
  {
    v15 = 1;
    v16 = Mso20Win32Client_52497(120, 2);
    if ( v16 )
      v11 = sub_1800AD3B4(v16, (_DWORD)a1, v14, v17, (__int64)a7);
    else
      v11 = 0;
    if ( !v11 )
      sub_180098E08(a7, 4294966285LL);
  }
  v24[0] = v14;
  if ( (*a7 & 8) != 0 )
    goto LABEL_32;
  sub_1800CA1A4(v24, v11, a7);
  if ( (*a7 & 8) != 0 )
    goto LABEL_32;
  v18 = Mso20Win32Client_52497(120, 2);
  if ( v18 )
    v10 = sub_1800ACE5C(v18, (__int64)a1, v14, a7);
  else
    v10 = 0;
  v19 = (*(_DWORD *)(v11 + 96))-- == 1;
  if ( v19 )
  {
    sub_1800AD474(v11);
    Mso20Win32Client_53248(v11);
  }
  v11 = 0;
  if ( v10 )
  {
    if ( (*a7 & 8) == 0 )
    {
      v20 = 0;
      while ( (*a7 & 8) == 0 )
      {
        sub_1800CA7E8(v24, v10, v20++, a7);
        if ( v20 >= 0x14 )
          goto LABEL_27;
      }
    }
    goto LABEL_32;
  }
  sub_180098E08(a7, 4294966285LL);
LABEL_27:
  if ( (*a7 & 8) != 0 )
    goto LABEL_32;
  if ( (unsigned __int8)a4 >= 2u && a4 < 65534 )
    sub_1800CAB30(v24, v10, a7);
  if ( (*a7 & 8) != 0 )
  {
LABEL_32:
    if ( v10 )
    {
      v19 = (*(_DWORD *)(v10 + 96))-- == 1;
      if ( v19 )
      {
        sub_1800AD474(v10);
        Mso20Win32Client_53248(v10);
      }
    }
    if ( v11 )
    {
      v19 = (*(_DWORD *)(v11 + 96))-- == 1;
      if ( v19 )
      {
        sub_1800AD474(v11);
        Mso20Win32Client_53248(v11);
      }
    }
    v10 = 0;
  }
  if ( v14 && _InterlockedExchangeAdd((volatile signed __int32 *)(v14 + 124), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v14)(v14, 1);
  if ( (*a7 & 8) != 0 && v15 == 1 )
  {
    v25[0] = 1;
    v25[8] = 0;
    sub_1800C9220(v13);
    if ( !DeleteFileW(a2) )
    {
      LastError = GetLastError();
      sub_1800C87AC(v22, v25, LastError);
    }
    if ( (v25[0] & 0xFFFFFFFE) != 0 )
      sub_180098D54(v25);
  }
  return v10;
}

```

## disassembly

```asm
0x1800bbd7c  mov     rax, rsp
0x1800bbd7f  mov     [rax+8], rbx
0x1800bbd83  mov     [rax+18h], rsi
0x1800bbd87  mov     [rax+20h], rdi
0x1800bbd8b  mov     [rax+10h], rdx
0x1800bbd8f  push    rbp
0x1800bbd90  push    r12
0x1800bbd92  push    r13
0x1800bbd94  push    r14
0x1800bbd96  push    r15
0x1800bbd98  mov     rbp, rsp
0x1800bbd9b  sub     rsp, 80h
0x1800bbda2  mov     r13d, r9d
0x1800bbda5  mov     r12, r8
0x1800bbda8  mov     r15, rcx
0x1800bbdab  xor     esi, esi
0x1800bbdad  xor     edi, edi
0x1800bbdaf  mov     [rbp+var_40], esi
0x1800bbdb2  lea     edx, [rsi+2]
0x1800bbdb5  mov     ecx, 530h
0x1800bbdba  call    cs:Mso20Win32Client_52497
0x1800bbdc0  mov     [rbp+var_30], rax
0x1800bbdc4  mov     rbx, [rbp+arg_30]
0x1800bbdc8  test    rax, rax
0x1800bbdcb  jz      short loc_1800BBDE0
0x1800bbdcd  mov     r8, rbx
0x1800bbdd0  mov     rdx, [r15]
0x1800bbdd3  mov     rcx, rax
0x1800bbdd6  call    sub_180090894
0x1800bbddb  mov     r14, rax
0x1800bbdde  jmp     short loc_1800BBDE3
0x1800bbde0  xor     r14d, r14d
0x1800bbde3  test    r14, r14
0x1800bbde6  jnz     short loc_1800BBDF5
0x1800bbde8  mov     edx, 0FFFFFC0Dh
0x1800bbded  mov     rcx, rbx
0x1800bbdf0  call    sub_180098E08
0x1800bbdf5  test    byte ptr [rbx], 8
0x1800bbdf8  jnz     short loc_1800BBE78
0x1800bbdfa  mov     [rsp+80h+var_48], rbx
0x1800bbdff  mov     rax, [rbp+arg_28]
0x1800bbe03  mov     [rsp+80h+var_50], rax
0x1800bbe08  mov     eax, [rbp+arg_20]
0x1800bbe0b  mov     [rsp+80h+var_58], eax
0x1800bbe0f  mov     dword ptr [rsp+80h+var_60], r13d
0x1800bbe14  mov     r9, r12
0x1800bbe17  mov     r8, [rbp+lpFileName]
0x1800bbe1b  mov     rdx, [r15+0F8h]
0x1800bbe22  mov     rcx, r14
0x1800bbe25  call    sub_1800916F8
0x1800bbe2a  test    byte ptr [rbx], 8
0x1800bbe2d  jnz     short loc_1800BBE78
0x1800bbe2f  mov     edx, 2
0x1800bbe34  lea     ecx, [rdx+76h]
0x1800bbe37  lea     r12d, [rdx-1]
0x1800bbe3b  call    cs:Mso20Win32Client_52497
0x1800bbe41  mov     [rbp+arg_30], rax
0x1800bbe45  test    rax, rax
0x1800bbe48  jz      short loc_1800BBE62
0x1800bbe4a  mov     [rsp+80h+var_60], rbx
0x1800bbe4f  mov     r8, r14
0x1800bbe52  mov     rdx, r15
0x1800bbe55  mov     rcx, rax
0x1800bbe58  call    sub_1800AD3B4
0x1800bbe5d  mov     rdi, rax
0x1800bbe60  jmp     short loc_1800BBE64
0x1800bbe62  xor     edi, edi
0x1800bbe64  test    rdi, rdi
0x1800bbe67  jnz     short loc_1800BBE7C
0x1800bbe69  mov     edx, 0FFFFFC0Dh
0x1800bbe6e  mov     rcx, rbx
0x1800bbe71  call    sub_180098E08
0x1800bbe76  jmp     short loc_1800BBE7C
0x1800bbe78  mov     r12d, [rbp+var_40]
0x1800bbe7c  mov     [rbp+var_38], r14
0x1800bbe80  test    byte ptr [rbx], 8
0x1800bbe83  jnz     loc_1800BBF4D
0x1800bbe89  mov     r8, rbx
0x1800bbe8c  mov     rdx, rdi
0x1800bbe8f  lea     rcx, [rbp+var_38]
0x1800bbe93  call    sub_1800CA1A4
0x1800bbe98  test    byte ptr [rbx], 8
0x1800bbe9b  jnz     loc_1800BBF4D
0x1800bbea1  mov     edx, 2
0x1800bbea6  lea     ecx, [rdx+76h]
0x1800bbea9  call    cs:Mso20Win32Client_52497
0x1800bbeaf  mov     [rbp+arg_30], rax
0x1800bbeb3  test    rax, rax
0x1800bbeb6  jz      short loc_1800BBECE
0x1800bbeb8  mov     r9, rbx
0x1800bbebb  mov     r8, r14
0x1800bbebe  mov     rdx, r15
0x1800bbec1  mov     rcx, rax
0x1800bbec4  call    sub_1800ACE5C
0x1800bbec9  mov     rsi, rax
0x1800bbecc  jmp     short loc_1800BBED0
0x1800bbece  xor     esi, esi
0x1800bbed0  sub     dword ptr [rdi+60h], 1
0x1800bbed4  jnz     short loc_1800BBEE7
0x1800bbed6  mov     rcx, rdi
0x1800bbed9  call    sub_1800AD474
0x1800bbede  mov     rcx, rdi
0x1800bbee1  call    cs:Mso20Win32Client_53248
0x1800bbee7  xor     edi, edi
0x1800bbee9  test    rsi, rsi
0x1800bbeec  jnz     short loc_1800BBEFD
0x1800bbeee  mov     edx, 0FFFFFC0Dh
0x1800bbef3  mov     rcx, rbx
0x1800bbef6  call    sub_180098E08
0x1800bbefb  jmp     short loc_1800BBF25
0x1800bbefd  test    byte ptr [rbx], 8
0x1800bbf00  jnz     short loc_1800BBF4D
0x1800bbf02  xor     r15d, r15d
0x1800bbf05  test    byte ptr [rbx], 8
0x1800bbf08  jnz     short loc_1800BBF4D
0x1800bbf0a  mov     r9, rbx
0x1800bbf0d  mov     r8d, r15d
0x1800bbf10  mov     rdx, rsi
0x1800bbf13  lea     rcx, [rbp+var_38]
0x1800bbf17  call    sub_1800CA7E8
0x1800bbf1c  inc     r15d
0x1800bbf1f  cmp     r15d, 14h
0x1800bbf23  jb      short loc_1800BBF05
0x1800bbf25  test    byte ptr [rbx], 8
0x1800bbf28  jnz     short loc_1800BBF4D
0x1800bbf2a  cmp     r13b, 2
0x1800bbf2e  jb      short loc_1800BBF48
0x1800bbf30  cmp     r13d, 0FFFEh
0x1800bbf37  jge     short loc_1800BBF48
0x1800bbf39  mov     r8, rbx
0x1800bbf3c  mov     rdx, rsi
0x1800bbf3f  lea     rcx, [rbp+var_38]
0x1800bbf43  call    sub_1800CAB30
0x1800bbf48  test    byte ptr [rbx], 8
0x1800bbf4b  jz      short loc_1800BBF87
0x1800bbf4d  test    rsi, rsi
0x1800bbf50  jz      short loc_1800BBF69
0x1800bbf52  sub     dword ptr [rsi+60h], 1
0x1800bbf56  jnz     short loc_1800BBF69
0x1800bbf58  mov     rcx, rsi
0x1800bbf5b  call    sub_1800AD474
0x1800bbf60  mov     rcx, rsi
0x1800bbf63  call    cs:Mso20Win32Client_53248
0x1800bbf69  test    rdi, rdi
0x1800bbf6c  jz      short loc_1800BBF85
0x1800bbf6e  sub     dword ptr [rdi+60h], 1
0x1800bbf72  jnz     short loc_1800BBF85
0x1800bbf74  mov     rcx, rdi
0x1800bbf77  call    sub_1800AD474
0x1800bbf7c  mov     rcx, rdi
0x1800bbf7f  call    cs:Mso20Win32Client_53248
0x1800bbf85  xor     esi, esi
0x1800bbf87  test    r14, r14
0x1800bbf8a  jz      short loc_1800BBFAE
0x1800bbf8c  or      eax, 0FFFFFFFFh
0x1800bbf8f  lock xadd [r14+7Ch], eax
0x1800bbf95  cmp     eax, 1
0x1800bbf98  jnz     short loc_1800BBFAE
0x1800bbf9a  mov     rax, [r14]
0x1800bbf9d  mov     edx, 1
0x1800bbfa2  mov     rcx, r14
0x1800bbfa5  mov     rax, [rax]
0x1800bbfa8  call    cs:__guard_dispatch_icall_fptr
0x1800bbfae  test    byte ptr [rbx], 8
0x1800bbfb1  jz      short loc_1800BBFFD
0x1800bbfb3  cmp     r12d, 1
0x1800bbfb7  jnz     short loc_1800BBFFD
0x1800bbfb9  mov     [rbp+var_28], r12d
0x1800bbfbd  mov     [rbp+var_8], 0
0x1800bbfc4  call    sub_1800C9220
0x1800bbfc9  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800bbfcd  call    cs:DeleteFileW
0x1800bbfd3  test    eax, eax
0x1800bbfd5  jnz     short loc_1800BBFEA
0x1800bbfd7  call    cs:GetLastError
0x1800bbfdd  mov     r8d, eax
0x1800bbfe0  lea     rdx, [rbp+var_28]
0x1800bbfe4  call    sub_1800C87AC
0x1800bbfe9  nop
0x1800bbfea  test    [rbp+var_28], 0FFFFFFFEh
0x1800bbff1  jz      short loc_1800BBFFD
0x1800bbff3  lea     rcx, [rbp+var_28]
0x1800bbff7  call    sub_180098D54
0x1800bbffc  nop
0x1800bbffd  mov     rax, rsi
0x1800bc000  lea     r11, [rsp+80h+var_s0]
0x1800bc008  mov     rbx, [r11+30h]
0x1800bc00c  mov     rsi, [r11+40h]
0x1800bc010  mov     rdi, [r11+48h]
0x1800bc014  mov     rsp, r11
0x1800bc017  pop     r15
0x1800bc019  pop     r14
0x1800bc01b  pop     r13
0x1800bc01d  pop     r12
0x1800bc01f  pop     rbp
0x1800bc020  retn
```
