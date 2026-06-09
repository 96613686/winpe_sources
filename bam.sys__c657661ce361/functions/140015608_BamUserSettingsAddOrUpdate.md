# BamUserSettingsAddOrUpdate

- ea: `0x140015608`
- end: `0x14001586f`
- name: `BamUserSettingsAddOrUpdate`
- size: `615`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _UNICODE_STRING *, int, int, char)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x14000c5b0`
- `0x140013d40`

## callees

- `0x140001430`
- `0x1400026d0`
- `0x140011a98`
- `0x140011b44`
- `0x140013624`
- `0x140015608`
- `0x140015878`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140015793`
- `ntoskrnl!ZwClose` at `0x140015793`
- `ntoskrnl!ZwSetValueKey` at `0x140015762`
- `ntoskrnl!ZwSetValueKey` at `0x140015762`

## pseudocode

```c
__int64 __fastcall BamUserSettingsAddOrUpdate(
        unsigned __int16 *a1,
        struct _UNICODE_STRING *a2,
        int a3,
        int a4,
        char a5)
{
  HANDLE v5; // rdi
  NTSTATUS updated; // ebx
  int v11; // eax
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  __int128 Data; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h]
  __int128 v18; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+70h] [rbp-90h]
  _BYTE v20[32]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD *v21; // [rsp+A0h] [rbp-60h]
  __int64 v22; // [rsp+A8h] [rbp-58h]
  __int64 v23; // [rsp+B0h] [rbp-50h]
  _DWORD v24[2]; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD *v25; // [rsp+C0h] [rbp-40h]
  __int64 v26; // [rsp+C8h] [rbp-38h]
  wchar_t *Buffer; // [rsp+D0h] [rbp-30h]
  _DWORD v28[2]; // [rsp+D8h] [rbp-28h] BYREF
  int *v29; // [rsp+E0h] [rbp-20h]
  __int64 v30; // [rsp+E8h] [rbp-18h]
  HANDLE *p_KeyHandle; // [rsp+F0h] [rbp-10h]
  __int64 v32; // [rsp+F8h] [rbp-8h]

  v5 = 0;
  v19 = 0;
  LOWORD(v13) = 0;
  v17 = 0;
  v18 = 0;
  KeyHandle = 0;
  Data = 0;
  if ( !BampUserSettingsContext )
  {
    updated = -1073741823;
    goto LABEL_22;
  }
  if ( a1 && a2 )
  {
    if ( a3 >= 3 )
    {
      updated = -1073741811;
      goto LABEL_22;
    }
    if ( !a4 )
    {
      updated = BamUserSettingsCheckOrigin(a2, &v13, (char *)&v13 + 1);
      if ( updated < 0 )
        goto LABEL_22;
      if ( (_WORD)v13 )
      {
        updated = -1073741637;
        goto LABEL_22;
      }
    }
    v11 = BampUserSettingsOpenUserKey(a1, 1, &KeyHandle);
    v5 = KeyHandle;
    updated = v11;
    if ( v11 >= 0 )
    {
      if ( (a5 & 1) != 0 )
      {
        if ( (int)BampUserSettingsReadEntry(KeyHandle, a2, &v18) < 0 )
          HIDWORD(v17) |= 2u;
        else
          HIDWORD(v17) = BYTE4(v19) & 2 | HIDWORD(v17) & 0xFFFFFFFD;
      }
      DWORD2(Data) = a3;
      LODWORD(v17) = a4;
      *(_QWORD *)&Data = MEMORY[0xFFFFF78000000014];
      updated = ZwSetValueKey(v5, a2, 0, 3u, &Data, 0x18u);
      if ( updated >= 0 )
      {
        updated = BampUserSettingsUpdateSequenceNumber(v5);
        if ( updated >= 0 )
          updated = 0;
      }
    }
  }
  else
  {
    updated = -1073741811;
  }
  if ( v5 )
    ZwClose(v5);
LABEL_22:
  if ( (unsigned int)dword_140007010 > 5 )
  {
    v22 = 2;
    v21 = v24;
    v23 = *((_QWORD *)a1 + 1);
    v24[0] = *a1;
    v25 = v28;
    Buffer = a2->Buffer;
    v28[0] = a2->Length;
    v29 = &v15;
    p_KeyHandle = &KeyHandle;
    v24[1] = 0;
    v26 = 2;
    v28[1] = 0;
    v30 = 4;
    LODWORD(KeyHandle) = updated;
    v32 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140007010, byte_1400058F3, 0, 0, 8, v20, v13, KeyHandle, a3);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140015608  push    rbp
0x14001560a  push    rbx
0x14001560b  push    rsi
0x14001560c  push    rdi
0x14001560d  push    r12
0x14001560f  push    r14
0x140015611  push    r15
0x140015613  lea     rbp, [rsp-10h]
0x140015618  sub     rsp, 110h
0x14001561f  mov     rax, cs:__security_cookie
0x140015626  xor     rax, rsp
0x140015629  mov     [rbp+40h+var_40], rax
0x14001562d  xor     eax, eax
0x14001562f  xor     edi, edi
0x140015631  cmp     qword ptr cs:BampUserSettingsContext, rax
0x140015638  xorps   xmm0, xmm0
0x14001563b  mov     r15d, r9d
0x14001563e  mov     [rsp+140h+var_D0], rax
0x140015643  mov     r12d, r8d
0x140015646  mov     [rsp+140h+var_110], al
0x14001564a  mov     rsi, rdx
0x14001564d  mov     [rsp+140h+var_10F], al
0x140015651  mov     r14, rcx
0x140015654  mov     [rsp+140h+var_E8], rax
0x140015659  movups  [rsp+140h+var_E0], xmm0
0x14001565e  mov     [rsp+140h+KeyHandle], rdi
0x140015663  movups  [rsp+140h+var_F8], xmm0
0x140015668  jnz     short loc_140015674
0x14001566a  mov     ebx, 0C0000001h
0x14001566f  jmp     loc_14001579F
0x140015674  test    r14, r14
0x140015677  jz      loc_140015786
0x14001567d  test    rsi, rsi
0x140015680  jz      loc_140015786
0x140015686  cmp     r12d, 3
0x14001568a  jl      short loc_140015696
0x14001568c  mov     ebx, 0C000000Dh
0x140015691  jmp     loc_14001579F
0x140015696  test    r15d, r15d
0x140015699  jnz     short loc_1400156CF
0x14001569b  lea     r8, [rsp+140h+var_10F]
0x1400156a0  mov     rcx, rsi
0x1400156a3  lea     rdx, [rsp+140h+var_110]
0x1400156a8  call    BamUserSettingsCheckOrigin
0x1400156ad  mov     ebx, eax
0x1400156af  test    eax, eax
0x1400156b1  js      loc_14001579F
0x1400156b7  cmp     [rsp+140h+var_110], dil
0x1400156bc  jnz     short loc_1400156C5
0x1400156be  cmp     [rsp+140h+var_10F], dil
0x1400156c3  jz      short loc_1400156CF
0x1400156c5  mov     ebx, 0C00000BBh
0x1400156ca  jmp     loc_14001579F
0x1400156cf  lea     r8, [rsp+140h+KeyHandle]
0x1400156d4  mov     edx, 1
0x1400156d9  mov     rcx, r14
0x1400156dc  call    BampUserSettingsOpenUserKey
0x1400156e1  mov     rdi, [rsp+140h+KeyHandle]
0x1400156e6  mov     ebx, eax
0x1400156e8  test    eax, eax
0x1400156ea  js      loc_14001578B
0x1400156f0  test    [rbp+40h+arg_20], 1
0x1400156f4  jz      short loc_140015725
0x1400156f6  lea     r8, [rsp+140h+var_E0]
0x1400156fb  mov     rdx, rsi
0x1400156fe  mov     rcx, rdi
0x140015701  call    BampUserSettingsReadEntry
0x140015706  test    eax, eax
0x140015708  js      short loc_140015720
0x14001570a  mov     ecx, dword ptr [rsp+140h+var_E8+4]
0x14001570e  mov     eax, dword ptr [rsp+140h+var_D0+4]
0x140015712  and     ecx, 0FFFFFFFDh
0x140015715  and     eax, 2
0x140015718  or      ecx, eax
0x14001571a  mov     dword ptr [rsp+140h+var_E8+4], ecx
0x14001571e  jmp     short loc_140015725
0x140015720  or      dword ptr [rsp+140h+var_E8+4], 2
0x140015725  mov     dword ptr [rsp+140h+var_F8+8], r12d
0x14001572a  mov     rax, 0FFFFF78000000014h
0x140015734  mov     dword ptr [rsp+140h+var_E8], r15d
0x140015739  mov     r9d, 3; Type
0x14001573f  mov     [rsp+140h+DataSize], 18h; DataSize
0x140015747  xor     r8d, r8d; TitleIndex
0x14001574a  mov     rdx, rsi; ValueName
0x14001574d  mov     rcx, rdi; KeyHandle
0x140015750  mov     rax, [rax]
0x140015753  mov     qword ptr [rsp+140h+var_F8], rax
0x140015758  lea     rax, [rsp+140h+var_F8]
0x14001575d  mov     [rsp+140h+Data], rax; Data
0x140015762  call    cs:__imp_ZwSetValueKey
0x140015769  nop     dword ptr [rax+rax+00h]
0x14001576e  mov     ebx, eax
0x140015770  test    eax, eax
0x140015772  js      short loc_14001578B
0x140015774  mov     rcx, rdi
0x140015777  call    BampUserSettingsUpdateSequenceNumber
0x14001577c  mov     ebx, eax
0x14001577e  test    eax, eax
0x140015780  js      short loc_14001578B
0x140015782  xor     ebx, ebx
0x140015784  jmp     short loc_14001578B
0x140015786  mov     ebx, 0C000000Dh
0x14001578b  test    rdi, rdi
0x14001578e  jz      short loc_14001579F
0x140015790  mov     rcx, rdi; Handle
0x140015793  call    cs:__imp_ZwClose
0x14001579a  nop     dword ptr [rax+rax+00h]
0x14001579f  mov     eax, cs:dword_140007010
0x1400157a5  cmp     eax, 5
0x1400157a8  jbe     loc_14001584E
0x1400157ae  lea     rax, [rbp+40h+var_88]
0x1400157b2  mov     [rbp+40h+var_98], 2
0x1400157ba  mov     [rbp+40h+var_A0], rax
0x1400157be  lea     rdx, byte_1400058F3
0x1400157c5  mov     rax, [r14+8]
0x1400157c9  lea     rcx, dword_140007010
0x1400157d0  mov     [rbp+40h+var_90], rax
0x1400157d4  xor     r9d, r9d
0x1400157d7  movzx   eax, word ptr [r14]
0x1400157db  xor     r8d, r8d
0x1400157de  mov     [rbp+40h+var_88], eax
0x1400157e1  lea     rax, [rbp+40h+var_68]
0x1400157e5  mov     [rbp+40h+var_80], rax
0x1400157e9  mov     rax, [rsi+8]
0x1400157ed  mov     [rbp+40h+var_70], rax
0x1400157f1  movzx   eax, word ptr [rsi]
0x1400157f4  mov     [rbp+40h+var_68], eax
0x1400157f7  lea     rax, [rsp+140h+var_100]
0x1400157fc  mov     [rbp+40h+var_60], rax
0x140015800  lea     rax, [rsp+140h+KeyHandle]
0x140015805  mov     [rbp+40h+var_50], rax
0x140015809  lea     rax, [rbp+40h+var_C0]
0x14001580d  mov     qword ptr [rsp+140h+DataSize], rax
0x140015812  mov     dword ptr [rsp+140h+Data], 8
0x14001581a  mov     [rbp+40h+var_84], 0
0x140015821  mov     [rbp+40h+var_78], 2
0x140015829  mov     [rbp+40h+var_64], 0
0x140015830  mov     [rsp+140h+var_100], r12d
0x140015835  mov     [rbp+40h+var_58], 4
0x14001583d  mov     dword ptr [rsp+140h+KeyHandle], ebx
0x140015841  mov     [rbp+40h+var_48], 4
0x140015849  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001584e  mov     eax, ebx
0x140015850  mov     rcx, [rbp+40h+var_40]
0x140015854  xor     rcx, rsp; StackCookie
0x140015857  call    __security_check_cookie
0x14001585c  add     rsp, 110h
0x140015863  pop     r15
0x140015865  pop     r14
0x140015867  pop     r12
0x140015869  pop     rdi
0x14001586a  pop     rsi
0x14001586b  pop     rbx
0x14001586c  pop     rbp
0x14001586d  retn
```
