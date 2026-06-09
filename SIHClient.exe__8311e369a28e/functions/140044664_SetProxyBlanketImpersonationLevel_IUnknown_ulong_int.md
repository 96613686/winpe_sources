# SetProxyBlanketImpersonationLevel(IUnknown *,ulong,int *)

- ea: `0x140044664`
- end: `0x140044844`
- name: `?SetProxyBlanketImpersonationLevel@@YAJPEAUIUnknown@@KPEAH@Z`
- size: `480`
- prototype: `__int64 __fastcall(struct IUnknown *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14003e814`

## callees

- `0x140008de4`
- `0x140044664`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004471d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400447f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004471d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400447f9`

## string_xrefs

- `0x1400447e0`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SetProxyBlanketImpersonationLevel(struct IUnknown *a1, __int64 a2, int *a3)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  int v6; // eax
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  LPVOID *p_pv; // [rsp+28h] [rbp-19h]
  LPVOID pv; // [rsp+68h] [rbp+27h] BYREF
  int v13; // [rsp+70h] [rbp+2Fh]
  unsigned int v14; // [rsp+74h] [rbp+33h] BYREF
  unsigned int v15; // [rsp+78h] [rbp+37h] BYREF
  __int64 v16; // [rsp+80h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A0h] [rbp+5Fh]

  v16 = 0;
  pv = 0;
  v15 = 0;
  v14 = 0;
  v13 = 0;
  if ( !a1 )
  {
    v4 = -2147467261;
    v5 = 27;
LABEL_6:
    v7 = v4;
    v8 = v5;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
      (const char *)v7,
      (int)p_pv);
    goto LABEL_14;
  }
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_0000013d_0000_0000_c000_000000000046,
         &v16);
  v4 = v6;
  if ( v6 >= 0 )
  {
    p_pv = &pv;
    v9 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, unsigned int *, unsigned int *))(*(_QWORD *)v16 + 24LL))(
           v16,
           a1,
           &v15,
           &v14);
    v4 = v9;
    if ( v9 >= 0 )
    {
      LODWORD(p_pv) = (_DWORD)pv;
      v9 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, _QWORD, _QWORD))(*(_QWORD *)v16 + 32LL))(
             v16,
             a1,
             v15,
             v14);
      v4 = v9;
      if ( v9 >= 0 )
        goto LABEL_13;
      v8 = 69;
    }
    else
    {
      v8 = 55;
    }
    v7 = (unsigned int)v9;
    goto LABEL_12;
  }
  if ( v6 != -2147467262 )
  {
    v5 = 32;
    goto LABEL_6;
  }
LABEL_13:
  v4 = 0;
LABEL_14:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return v4;
}

```

## disassembly

```asm
0x140044664  mov     rax, rsp
0x140044667  mov     [rax+10h], rbx
0x14004466b  mov     [rax+18h], rsi
0x14004466f  mov     [rax+20h], rdi
0x140044673  push    rbp
0x140044674  lea     rbp, [rax-5Fh]
0x140044678  sub     rsp, 90h
0x14004467f  mov     rax, cs:__security_cookie
0x140044686  xor     rax, rsp
0x140044689  mov     [rbp+57h+var_10], rax
0x14004468d  mov     rdi, rcx
0x140044690  mov     [rbp+57h+var_40], 0
0x140044698  mov     [rbp+57h+var_18], 0
0x1400446a0  mov     [rbp+57h+pv], 0
0x1400446a8  mov     [rbp+57h+var_20], 0
0x1400446af  mov     [rbp+57h+var_24], 0
0x1400446b6  mov     [rbp+57h+var_28], 0
0x1400446bd  mov     [rbp+57h+var_38], 0
0x1400446c4  test    rcx, rcx
0x1400446c7  jnz     short loc_1400446D3
0x1400446c9  mov     ebx, 80004003h
0x1400446ce  lea     eax, [rcx+1Bh]
0x1400446d1  jmp     short loc_1400446FF
0x1400446d3  mov     rax, [rcx]
0x1400446d6  lea     r8, [rbp+57h+var_18]
0x1400446da  lea     rdx, _GUID_0000013d_0000_0000_c000_000000000046
0x1400446e1  mov     rax, [rax]
0x1400446e4  call    _guard_dispatch_icall
0x1400446e9  mov     ebx, eax
0x1400446eb  test    eax, eax
0x1400446ed  jns     short loc_140044709
0x1400446ef  cmp     eax, 80004002h
0x1400446f4  jz      loc_1400447EE
0x1400446fa  mov     eax, 20h ; ' '
0x1400446ff  mov     r9d, ebx
0x140044702  mov     edx, eax
0x140044704  jmp     loc_1400447DC
0x140044709  mov     rbx, [rbp+57h+var_18]
0x14004470d  mov     rax, [rbx]
0x140044710  mov     rsi, [rax+18h]
0x140044714  mov     rcx, [rbp+57h+pv]; pv
0x140044718  test    rcx, rcx
0x14004471b  jz      short loc_14004472B
0x14004471d  call    cs:__imp_CoTaskMemFree
0x140044723  mov     [rbp+57h+pv], 0
0x14004472b  lea     rax, [rbp+57h+var_38]
0x14004472f  mov     [rsp+90h+var_50], rax
0x140044734  lea     rax, [rbp+57h+var_40]
0x140044738  mov     [rsp+90h+var_58], rax
0x14004473d  mov     [rsp+90h+var_60], 0
0x140044746  lea     rax, [rbp+57h+var_28]
0x14004474a  mov     [rsp+90h+var_68], rax
0x14004474f  lea     rax, [rbp+57h+pv]
0x140044753  mov     qword ptr [rsp+90h+var_70], rax
0x140044758  lea     r9, [rbp+57h+var_24]
0x14004475c  lea     r8, [rbp+57h+var_20]
0x140044760  mov     rdx, rdi
0x140044763  mov     rcx, rbx
0x140044766  mov     rax, rsi
0x140044769  call    _guard_dispatch_icall
0x14004476e  mov     ebx, eax
0x140044770  test    eax, eax
0x140044772  jns     short loc_14004477B
0x140044774  mov     edx, 37h ; '7'
0x140044779  jmp     short loc_1400447D9
0x14004477b  mov     r8d, [rbp+57h+var_38]
0x14004477f  and     r8d, 0FFFFFFBFh
0x140044783  or      r8d, 20h
0x140044787  mov     [rbp+57h+var_38], r8d
0x14004478b  mov     r10, [rbp+57h+var_40]
0x14004478f  mov     r11d, [rbp+57h+var_28]
0x140044793  mov     rbx, [rbp+57h+pv]
0x140044797  mov     rcx, [rbp+57h+var_18]
0x14004479b  mov     rax, [rcx]
0x14004479e  mov     dword ptr [rsp+90h+var_50], r8d
0x1400447a3  mov     [rsp+90h+var_58], r10
0x1400447a8  mov     dword ptr [rsp+90h+var_60], 3
0x1400447b0  mov     dword ptr [rsp+90h+var_68], r11d
0x1400447b5  mov     qword ptr [rsp+90h+var_70], rbx; int
0x1400447ba  mov     r9d, [rbp+57h+var_24]
0x1400447be  mov     r8d, [rbp+57h+var_20]
0x1400447c2  mov     rdx, rdi
0x1400447c5  mov     rax, [rax+20h]
0x1400447c9  call    _guard_dispatch_icall
0x1400447ce  mov     ebx, eax
0x1400447d0  test    eax, eax
0x1400447d2  jns     short loc_1400447EE
0x1400447d4  mov     edx, 45h ; 'E'; void *
0x1400447d9  mov     r9d, eax; char *
0x1400447dc  mov     rcx, [rbp+5Fh]; this
0x1400447e0  lea     r8, aCW1SSrcClientL_37; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400447e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400447ec  jmp     short loc_1400447F0
0x1400447ee  xor     ebx, ebx
0x1400447f0  mov     rcx, [rbp+57h+pv]; pv
0x1400447f4  test    rcx, rcx
0x1400447f7  jz      short loc_140044807
0x1400447f9  call    cs:__imp_CoTaskMemFree
0x1400447ff  mov     [rbp+57h+pv], 0
0x140044807  mov     rcx, [rbp+57h+var_18]
0x14004480b  test    rcx, rcx
0x14004480e  jz      short loc_14004481D
0x140044810  mov     rdx, [rcx]
0x140044813  mov     rax, [rdx+10h]
0x140044817  call    _guard_dispatch_icall
0x14004481c  nop
0x14004481d  mov     eax, ebx
0x14004481f  mov     rcx, [rbp+57h+var_10]
0x140044823  xor     rcx, rsp; StackCookie
0x140044826  call    __security_check_cookie
0x14004482b  lea     r11, [rsp+90h+var_s0]
0x140044833  mov     rbx, [r11+18h]
0x140044837  mov     rsi, [r11+20h]
0x14004483b  mov     rdi, [r11+28h]
0x14004483f  mov     rsp, r11
0x140044842  pop     rbp
0x140044843  retn
```
