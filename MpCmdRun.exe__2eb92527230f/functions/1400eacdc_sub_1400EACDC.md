# sub_1400EACDC

- ea: `0x1400eacdc`
- end: `0x1400eaeae`
- name: `sub_1400EACDC`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400edc94`

## callees

- `0x14000b750`
- `0x14000b830`
- `0x140036780`
- `0x14008133c`
- `0x140081450`
- `0x1400eacdc`
- `0x140115914`
- `0x140120340`

## import_xrefs

- `MpClient!MpClientUtilExportFunctions` at `0x1400ead21`
- `MpClient!MpClientUtilExportFunctions` at `0x1400ead21`
- `MpClient!MpConfigClose` at `0x1400eadad`
- `MpClient!MpConfigClose` at `0x1400eae7c`
- `MpClient!MpConfigClose` at `0x1400eadad`
- `MpClient!MpConfigClose` at `0x1400eae7c`
- `MpClient!MpConfigOpen` at `0x1400ead67`
- `MpClient!MpConfigOpen` at `0x1400eadff`
- `MpClient!MpConfigOpen` at `0x1400ead67`
- `MpClient!MpConfigOpen` at `0x1400eadff`

## pseudocode

```c
__int64 __fastcall sub_1400EACDC(_DWORD *a1)
{
  int v2; // ebx
  __int64 v3; // rax
  int v4; // eax
  int v5; // edi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-20h] BYREF
  __int64 v10; // [rsp+28h] [rbp-18h] BYREF

  v2 = 0;
  *a1 = 0;
  if ( !(unsigned int)sub_14000B750() )
  {
    if ( !(unsigned __int8)sub_14000B830() )
      return 0;
    v9 = 0;
    v3 = ((__int64 (*)(void))MpClientUtilExportFunctions)();
    if ( (*(int (__fastcall **)(int *))(v3 + 48))(&v9) < 0 || v9 != 2 )
      return 0;
  }
  v9 = 0;
  v4 = sub_140115914();
  v10 = 0;
  if ( v4 )
  {
    v5 = MpConfigOpen(L"Features", &v10);
    if ( v5 < 0 )
    {
      v6 = off_14018DE50;
      if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
      {
        v7 = 17;
        goto LABEL_10;
      }
      goto LABEL_11;
    }
    v5 = sub_14008133C(v10, L"ForcePassiveMode", &v9);
    if ( v5 < 0 )
    {
      v6 = off_14018DE50;
      if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
      {
        v7 = 18;
        goto LABEL_10;
      }
      goto LABEL_11;
    }
LABEL_26:
    if ( v10 )
      MpConfigClose(v10);
    LOBYTE(v2) = v9 == 1;
    *a1 = v2;
    return 0;
  }
  v5 = MpConfigOpen(L".", &v10);
  if ( v5 < 0 )
  {
    v6 = off_14018DE50;
    if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
    {
      v7 = 15;
LABEL_10:
      sub_140081450(v6[2], v7, qword_1401688E8, (unsigned int)v5);
      goto LABEL_11;
    }
    goto LABEL_11;
  }
  v5 = sub_14008133C(v10, L"PassiveMode", &v9);
  if ( v5 >= 0 )
    goto LABEL_26;
  v6 = off_14018DE50;
  if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
  {
    v7 = 16;
    goto LABEL_10;
  }
LABEL_11:
  if ( v10 )
    MpConfigClose(v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400eacdc  mov     [rsp-8+arg_8], rbx
0x1400eace1  mov     [rsp-8+arg_10], rsi
0x1400eace6  mov     [rsp-8+arg_18], rdi
0x1400eaceb  push    rbp
0x1400eacec  mov     rbp, rsp
0x1400eacef  sub     rsp, 40h
0x1400eacf3  mov     rax, cs:__security_cookie
0x1400eacfa  xor     rax, rsp
0x1400eacfd  mov     [rbp+var_10], rax
0x1400ead01  mov     rsi, rcx
0x1400ead04  xor     ebx, ebx
0x1400ead06  mov     [rcx], ebx
0x1400ead08  call    sub_14000B750
0x1400ead0d  test    eax, eax
0x1400ead0f  jnz     short loc_1400EAD48
0x1400ead11  call    sub_14000B830
0x1400ead16  test    al, al
0x1400ead18  jz      loc_1400EAE8B
0x1400ead1e  mov     [rbp+var_20], ebx
0x1400ead21  call    cs:MpClientUtilExportFunctions
0x1400ead27  lea     rcx, [rbp+var_20]
0x1400ead2b  mov     rax, [rax+30h]
0x1400ead2f  call    cs:__guard_dispatch_icall_fptr
0x1400ead35  nop
0x1400ead36  test    eax, eax
0x1400ead38  js      loc_1400EAE8B
0x1400ead3e  cmp     [rbp+var_20], 2
0x1400ead42  jnz     loc_1400EAE8B
0x1400ead48  mov     [rbp+var_20], ebx
0x1400ead4b  call    sub_140115914
0x1400ead50  mov     [rbp+var_18], rbx
0x1400ead54  lea     rdx, [rbp+var_18]
0x1400ead58  test    eax, eax
0x1400ead5a  jnz     loc_1400EADF8
0x1400ead60  lea     rcx, asc_140147054; "."
0x1400ead67  call    cs:MpConfigOpen
0x1400ead6d  mov     edi, eax
0x1400ead6f  test    eax, eax
0x1400ead71  jns     short loc_1400EADBA
0x1400ead73  lea     rdx, off_14018DE50
0x1400ead7a  mov     rcx, cs:off_14018DE50
0x1400ead81  cmp     rcx, rdx
0x1400ead84  jz      short loc_1400EADA4
0x1400ead86  test    byte ptr [rcx+1Ch], 1
0x1400ead8a  jz      short loc_1400EADA4
0x1400ead8c  mov     edx, 0Fh
0x1400ead91  mov     r9d, edi
0x1400ead94  lea     r8, qword_1401688E8
0x1400ead9b  mov     rcx, [rcx+10h]
0x1400ead9f  call    sub_140081450
0x1400eada4  mov     rcx, [rbp+var_18]
0x1400eada8  test    rcx, rcx
0x1400eadab  jz      short loc_1400EADB3
0x1400eadad  call    cs:MpConfigClose
0x1400eadb3  mov     eax, edi
0x1400eadb5  jmp     loc_1400EAE8D
0x1400eadba  lea     r8, [rbp+var_20]
0x1400eadbe  lea     rdx, aPassivemode; "PassiveMode"
0x1400eadc5  mov     rcx, [rbp+var_18]
0x1400eadc9  call    sub_14008133C
0x1400eadce  mov     edi, eax
0x1400eadd0  test    eax, eax
0x1400eadd2  jns     loc_1400EAE73
0x1400eadd8  lea     rdx, off_14018DE50
0x1400eaddf  mov     rcx, cs:off_14018DE50
0x1400eade6  cmp     rcx, rdx
0x1400eade9  jz      short loc_1400EADA4
0x1400eadeb  test    byte ptr [rcx+1Ch], 1
0x1400eadef  jz      short loc_1400EADA4
0x1400eadf1  mov     edx, 10h
0x1400eadf6  jmp     short loc_1400EAD91
0x1400eadf8  lea     rcx, aFeatures; "Features"
0x1400eadff  call    cs:MpConfigOpen
0x1400eae05  mov     edi, eax
0x1400eae07  test    eax, eax
0x1400eae09  jns     short loc_1400EAE2E
0x1400eae0b  lea     rdx, off_14018DE50
0x1400eae12  mov     rcx, cs:off_14018DE50
0x1400eae19  cmp     rcx, rdx
0x1400eae1c  jz      short loc_1400EADA4
0x1400eae1e  test    byte ptr [rcx+1Ch], 1
0x1400eae22  jz      short loc_1400EADA4
0x1400eae24  mov     edx, 11h
0x1400eae29  jmp     loc_1400EAD91
0x1400eae2e  lea     r8, [rbp+var_20]
0x1400eae32  lea     rdx, aForcepassivemo; "ForcePassiveMode"
0x1400eae39  mov     rcx, [rbp+var_18]
0x1400eae3d  call    sub_14008133C
0x1400eae42  mov     edi, eax
0x1400eae44  test    eax, eax
0x1400eae46  jns     short loc_1400EAE73
0x1400eae48  lea     rdx, off_14018DE50
0x1400eae4f  mov     rcx, cs:off_14018DE50
0x1400eae56  cmp     rcx, rdx
0x1400eae59  jz      loc_1400EADA4
0x1400eae5f  test    byte ptr [rcx+1Ch], 1
0x1400eae63  jz      loc_1400EADA4
0x1400eae69  mov     edx, 12h
0x1400eae6e  jmp     loc_1400EAD91
0x1400eae73  mov     rcx, [rbp+var_18]
0x1400eae77  test    rcx, rcx
0x1400eae7a  jz      short loc_1400EAE82
0x1400eae7c  call    cs:MpConfigClose
0x1400eae82  cmp     [rbp+var_20], 1
0x1400eae86  setz    bl
0x1400eae89  mov     [rsi], ebx
0x1400eae8b  xor     eax, eax
0x1400eae8d  mov     rcx, [rbp+var_10]
0x1400eae91  xor     rcx, rsp; StackCookie
0x1400eae94  call    __security_check_cookie
0x1400eae99  mov     rbx, [rsp+40h+arg_8]
0x1400eae9e  mov     rsi, [rsp+40h+arg_10]
0x1400eaea3  mov     rdi, [rsp+40h+arg_18]
0x1400eaea8  add     rsp, 40h
0x1400eaeac  pop     rbp
0x1400eaead  retn
```
