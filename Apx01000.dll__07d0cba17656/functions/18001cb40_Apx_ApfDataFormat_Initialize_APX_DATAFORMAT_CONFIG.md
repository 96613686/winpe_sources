# Apx::ApfDataFormat::Initialize(_APX_DATAFORMAT_CONFIG *)

- ea: `0x18001cb40`
- end: `0x18001cc55`
- name: `?Initialize@ApfDataFormat@Apx@@AEAAJPEAU_APX_DATAFORMAT_CONFIG@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(Apx::ApfDataFormat *this, union KSDATAFORMAT **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001d4fc`

## callees

- `0x18000a12c`
- `0x18000be74`
- `0x18001c924`
- `0x18001cb40`
- `0x18001d188`

## pseudocode

```c
__int64 __fastcall Apx::ApfDataFormat::Initialize(Apx::ApfDataFormat *this, union KSDATAFORMAT **a2)
{
  _QWORD *v4; // rcx
  int v5; // ebx
  char *v6; // r14

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)a2 + 2) )
  {
    v5 = Apx::ApfDataFormat::ValidateKsFormat(this, a2[2]);
    if ( v5 >= 0 )
    {
      v6 = (char *)this + 16;
      v5 = Apx::ApfDataFormat::DuplicateKsFormat(
             (Apx::ApfDataFormat *)((char *)this + 32),
             a2[2],
             (union KSDATAFORMAT **)this + 2,
             (struct tWAVEFORMATEX **)this + 3,
             (struct WAVEFORMATEXTENSIBLE **)this + 4,
             (struct WAVEFORMATEXTENSIBLE_IEC61937 **)this + 5);
      if ( v5 >= 0 )
      {
        *(_DWORD *)(*(_QWORD *)v6 + 4LL) &= ~2u;
        v5 = 0;
        *(_DWORD *)(*(_QWORD *)v6 + 8LL) = 0;
      }
    }
    goto LABEL_13;
  }
  v5 = -2147024809;
  if ( v4 == &WPP_GLOBAL_Control )
    return (unsigned int)v5;
  if ( (*((_BYTE *)v4 + 28) & 0x20) != 0 && *((_BYTE *)v4 + 25) >= 2u )
  {
    WPP_SF_dd(v4[2], 21, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids);
LABEL_13:
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_(v4[2], 22, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001cb40  push    rbx
0x18001cb42  push    rbp
0x18001cb43  push    rsi
0x18001cb44  push    rdi
0x18001cb45  push    r14
0x18001cb47  sub     rsp, 30h
0x18001cb4b  mov     rsi, rdx
0x18001cb4e  mov     rdi, rcx
0x18001cb51  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb58  lea     rbp, WPP_GLOBAL_Control
0x18001cb5f  cmp     rcx, rbp
0x18001cb62  jz      short loc_18001CB8C
0x18001cb64  test    byte ptr [rcx+1Ch], 1
0x18001cb68  jz      short loc_18001CB8C
0x18001cb6a  cmp     byte ptr [rcx+19h], 5
0x18001cb6e  jb      short loc_18001CB8C
0x18001cb70  mov     rcx, [rcx+10h]
0x18001cb74  lea     r8, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids
0x18001cb7b  mov     edx, 14h
0x18001cb80  call    WPP_SF_
0x18001cb85  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb8c  mov     r9d, [rsi+8]
0x18001cb90  test    r9d, r9d
0x18001cb93  jz      short loc_18001CBCA
0x18001cb95  mov     ebx, 80070057h
0x18001cb9a  cmp     rcx, rbp
0x18001cb9d  jz      loc_18001CC48
0x18001cba3  test    byte ptr [rcx+1Ch], 20h
0x18001cba7  jz      short loc_18001CC22
0x18001cba9  cmp     byte ptr [rcx+19h], 2
0x18001cbad  jb      short loc_18001CC22
0x18001cbaf  mov     rcx, [rcx+10h]
0x18001cbb3  lea     r8, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids
0x18001cbba  mov     edx, 15h
0x18001cbbf  mov     dword ptr [rsp+58h+var_38], ebx
0x18001cbc3  call    WPP_SF_dd
0x18001cbc8  jmp     short loc_18001CC1B
0x18001cbca  mov     rdx, [rsi+10h]; union KSDATAFORMAT *
0x18001cbce  mov     rcx, rdi; this
0x18001cbd1  call    ?ValidateKsFormat@ApfDataFormat@Apx@@AEAAJPEATKSDATAFORMAT@@@Z; Apx::ApfDataFormat::ValidateKsFormat(KSDATAFORMAT *)
0x18001cbd6  mov     ebx, eax
0x18001cbd8  test    eax, eax
0x18001cbda  js      short loc_18001CC1B
0x18001cbdc  mov     rdx, [rsi+10h]; union KSDATAFORMAT *
0x18001cbe0  lea     rax, [rdi+28h]
0x18001cbe4  lea     rcx, [rdi+20h]; this
0x18001cbe8  mov     [rsp+58h+var_30], rax; struct WAVEFORMATEXTENSIBLE_IEC61937 **
0x18001cbed  lea     r14, [rdi+10h]
0x18001cbf1  mov     [rsp+58h+var_38], rcx; struct WAVEFORMATEXTENSIBLE **
0x18001cbf6  mov     r8, r14; union KSDATAFORMAT **
0x18001cbf9  lea     r9, [rdi+18h]; struct tWAVEFORMATEX **
0x18001cbfd  call    ?DuplicateKsFormat@ApfDataFormat@Apx@@AEAAJPEATKSDATAFORMAT@@PEAPEAT3@PEAPEAUtWAVEFORMATEX@@PEAPEAUWAVEFORMATEXTENSIBLE@@PEAPEAUWAVEFORMATEXTENSIBLE_IEC61937@@@Z; Apx::ApfDataFormat::DuplicateKsFormat(KSDATAFORMAT *,KSDATAFORMAT * *,tWAVEFORMATEX * *,WAVEFORMATEXTENSIBLE * *,WAVEFORMATEXTENSIBLE_IEC61937 * *)
0x18001cc02  mov     ebx, eax
0x18001cc04  test    eax, eax
0x18001cc06  js      short loc_18001CC1B
0x18001cc08  mov     rax, [r14]
0x18001cc0b  and     dword ptr [rax+4], 0FFFFFFFDh
0x18001cc0f  mov     rax, [r14]
0x18001cc12  xor     ebx, ebx
0x18001cc14  mov     dword ptr [rax+8], 0
0x18001cc1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc22  cmp     rcx, rbp
0x18001cc25  jz      short loc_18001CC48
0x18001cc27  test    byte ptr [rcx+1Ch], 1
0x18001cc2b  jz      short loc_18001CC48
0x18001cc2d  cmp     byte ptr [rcx+19h], 5
0x18001cc31  jb      short loc_18001CC48
0x18001cc33  mov     rcx, [rcx+10h]
0x18001cc37  lea     r8, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids
0x18001cc3e  mov     edx, 16h
0x18001cc43  call    WPP_SF_
0x18001cc48  mov     eax, ebx
0x18001cc4a  add     rsp, 30h
0x18001cc4e  pop     r14
0x18001cc50  pop     rdi
0x18001cc51  pop     rsi
0x18001cc52  pop     rbp
0x18001cc53  pop     rbx
0x18001cc54  retn
```
