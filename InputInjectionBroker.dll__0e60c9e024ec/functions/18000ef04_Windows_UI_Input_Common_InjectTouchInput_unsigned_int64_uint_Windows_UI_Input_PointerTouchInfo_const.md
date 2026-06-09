# Windows::UI::Input::Common::InjectTouchInput(unsigned __int64,uint,Windows::UI::Input::PointerTouchInfo * const)

- ea: `0x18000ef04`
- end: `0x18000f0b8`
- name: `?InjectTouchInput@Common@Input@UI@Windows@@YAJ_KIQEAUPointerTouchInfo@234@@Z`
- size: `436`
- prototype: `__int64 __fastcall(Windows::UI::Input::Common *this, unsigned int, __int64, struct Windows::UI::Input::PointerTouchInfo *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006dd0`

## callees

- `0x18000ee6c`
- `0x18000ef04`
- `0x18001143a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f07a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f07a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f099`
- `ext-ms-win-ntuser-rim-l1-1-0!InjectPointerInput` at `0x18000f070`
- `ext-ms-win-ntuser-rim-l1-1-0!InjectPointerInput` at `0x18000f070`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Common::InjectTouchInput(
        Windows::UI::Input::Common *this,
        unsigned int a2,
        __int64 a3,
        struct Windows::UI::Input::PointerTouchInfo *const a4)
{
  unsigned __int64 v5; // rsi
  _BYTE *v7; // rdi
  void *v8; // rcx
  unsigned int v9; // ebx
  _BYTE *v10; // rdx
  _BYTE *v11; // r9
  unsigned int v12; // r10d
  int v13; // eax
  __int64 v14; // r11
  __int64 v15; // r8
  __int64 v16; // rcx
  int v17; // eax
  signed int LastError; // eax
  _BYTE v20[200]; // [rsp+20h] [rbp-C8h] BYREF
  void *pv; // [rsp+F0h] [rbp+8h] BYREF

  v5 = a2;
  v7 = 0;
  pv = 0;
  memset_0(v20, 0, 0x98u);
  if ( (_DWORD)v5 == 1 )
  {
    v9 = 0;
    v10 = v20;
    v11 = v20;
    v12 = 0;
LABEL_6:
    v14 = 0;
    do
    {
      v15 = 152 * v14;
      v16 = 9 * v14;
      ++v12;
      v17 = *(_DWORD *)(a3 + 72 * v14++ + 52);
      *(_DWORD *)&v11[v15 + 124] = v17;
      *(_DWORD *)&v11[v15 + 116] = *(_DWORD *)(a3 + 8 * v16 + 48);
      *(_DWORD *)&v11[v15 + 112] = *(_DWORD *)(a3 + 8 * v16 + 44);
      *(_DWORD *)&v11[v15 + 120] = *(_DWORD *)(a3 + 8 * v16 + 56);
      *(_DWORD *)&v11[v15 + 8] = *(_DWORD *)(a3 + 8 * v16);
      *(_DWORD *)&v11[v15 + 12] = *(_DWORD *)(a3 + 8 * v16 + 4);
      *(_DWORD *)&v11[v15 + 16] = *(_DWORD *)(a3 + 8 * v16 + 8);
      *(_DWORD *)&v11[v15 + 20] = *(_DWORD *)(a3 + 8 * v16 + 12);
      *(_DWORD *)&v11[v15 + 40] = *(_DWORD *)(a3 + 8 * v16 + 16);
      *(_DWORD *)&v11[v15 + 44] = *(_DWORD *)(a3 + 8 * v16 + 20);
      *(_DWORD *)&v11[v15 + 72] = *(_DWORD *)(a3 + 8 * v16 + 24);
      *(_QWORD *)&v11[v15 + 88] = *(_QWORD *)(a3 + 8 * v16 + 32);
      *(_DWORD *)&v11[v15 + 148] = *(_DWORD *)(a3 + 8 * v16 + 64);
      *(_DWORD *)&v11[v15 + 108] = *(_DWORD *)(a3 + 8 * v16 + 40);
      *(_DWORD *)&v11[v15 + 144] = *(_DWORD *)(a3 + 8 * v16 + 60);
      *(_DWORD *)&v11[v15 + 8] = 2;
      *(_DWORD *)&v11[v15] = 2;
    }
    while ( v12 < (unsigned int)v5 );
LABEL_8:
    if ( !(unsigned int)InjectPointerInput(this, v10, (unsigned int)v5) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    goto LABEL_12;
  }
  if ( !is_mul_ok(v5, 0x98u) )
  {
    v9 = -2147024362;
    goto LABEL_12;
  }
  v13 = CTCoAllocPolicy::Alloc(v8, (v5 * (unsigned __int128)0x98uLL) >> 64, 152 * v5, &pv);
  v7 = pv;
  v9 = v13;
  if ( v13 >= 0 )
  {
    memset_0(pv, 0, 152 * v5);
    v12 = 0;
    v10 = v7;
    v11 = v7;
    if ( !(_DWORD)v5 )
      goto LABEL_8;
    goto LABEL_6;
  }
LABEL_12:
  CoTaskMemFree(v7);
  return v9;
}

```

## disassembly

```asm
0x18000ef04  mov     rax, rsp
0x18000ef07  mov     [rax+10h], rbx
0x18000ef0b  push    rbp
0x18000ef0c  push    rsi
0x18000ef0d  push    rdi
0x18000ef0e  push    r14
0x18000ef10  push    r15
0x18000ef12  sub     rsp, 0C0h
0x18000ef19  mov     r14, r8
0x18000ef1c  mov     esi, edx
0x18000ef1e  mov     r15, rcx
0x18000ef21  mov     ebx, 98h
0x18000ef26  xor     edi, edi
0x18000ef28  lea     rcx, [rsp+0E8h+var_C8]; void *
0x18000ef2d  mov     r8d, ebx; Size
0x18000ef30  mov     [rax+8], rdi
0x18000ef34  xor     edx, edx; Val
0x18000ef36  call    memset_0
0x18000ef3b  cmp     esi, 1
0x18000ef3e  jnz     short loc_18000EF4F
0x18000ef40  xor     ebx, ebx
0x18000ef42  lea     rdx, [rsp+0E8h+var_C8]
0x18000ef47  mov     r9, rdx
0x18000ef4a  xor     r10d, r10d
0x18000ef4d  jmp     short loc_18000EFA5
0x18000ef4f  mov     rax, rbx
0x18000ef52  mov     rbp, rsi
0x18000ef55  mul     rsi
0x18000ef58  test    rdx, rdx
0x18000ef5b  jnz     loc_18000F091
0x18000ef61  lea     r9, [rsp+0E8h+pv]; void **
0x18000ef69  mov     r8, rax; unsigned __int64
0x18000ef6c  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000ef71  mov     rdi, [rsp+0E8h+pv]
0x18000ef79  mov     ebx, eax
0x18000ef7b  test    eax, eax
0x18000ef7d  js      loc_18000F096
0x18000ef83  imul    r8, rbp, 98h; Size
0x18000ef8a  xor     edx, edx; Val
0x18000ef8c  mov     rcx, rdi; void *
0x18000ef8f  call    memset_0
0x18000ef94  xor     r10d, r10d
0x18000ef97  mov     rdx, rdi
0x18000ef9a  mov     r9, rdi
0x18000ef9d  test    esi, esi
0x18000ef9f  jz      loc_18000F06A
0x18000efa5  xor     r11d, r11d
0x18000efa8  lea     ebp, [r11+2]
0x18000efac  imul    r8, r11, 98h
0x18000efb3  lea     rcx, [r11+r11*8]
0x18000efb7  inc     r10d
0x18000efba  mov     eax, [r14+rcx*8+34h]
0x18000efbf  inc     r11
0x18000efc2  mov     [r8+r9+7Ch], eax
0x18000efc7  mov     eax, [r14+rcx*8+30h]
0x18000efcc  mov     [r8+r9+74h], eax
0x18000efd1  mov     eax, [r14+rcx*8+2Ch]
0x18000efd6  mov     [r8+r9+70h], eax
0x18000efdb  mov     eax, [r14+rcx*8+38h]
0x18000efe0  mov     [r8+r9+78h], eax
0x18000efe5  mov     eax, [r14+rcx*8]
0x18000efe9  mov     [r8+r9+8], eax
0x18000efee  mov     eax, [r14+rcx*8+4]
0x18000eff3  mov     [r8+r9+0Ch], eax
0x18000eff8  mov     eax, [r14+rcx*8+8]
0x18000effd  mov     [r8+r9+10h], eax
0x18000f002  mov     eax, [r14+rcx*8+0Ch]
0x18000f007  mov     [r8+r9+14h], eax
0x18000f00c  mov     eax, [r14+rcx*8+10h]
0x18000f011  mov     [r8+r9+28h], eax
0x18000f016  mov     eax, [r14+rcx*8+14h]
0x18000f01b  mov     [r8+r9+2Ch], eax
0x18000f020  mov     eax, [r14+rcx*8+18h]
0x18000f025  mov     [r8+r9+48h], eax
0x18000f02a  mov     rax, [r14+rcx*8+20h]
0x18000f02f  mov     [r8+r9+58h], rax
0x18000f034  mov     eax, [r14+rcx*8+40h]
0x18000f039  mov     [r8+r9+94h], eax
0x18000f041  mov     eax, [r14+rcx*8+28h]
0x18000f046  mov     [r8+r9+6Ch], eax
0x18000f04b  mov     eax, [r14+rcx*8+3Ch]
0x18000f050  mov     [r8+r9+90h], eax
0x18000f058  mov     [r8+r9+8], ebp
0x18000f05d  mov     [r8+r9], ebp
0x18000f061  cmp     r10d, esi
0x18000f064  jb      loc_18000EFAC
0x18000f06a  mov     r8d, esi
0x18000f06d  mov     rcx, r15
0x18000f070  call    cs:__imp_InjectPointerInput
0x18000f076  test    eax, eax
0x18000f078  jnz     short loc_18000F096
0x18000f07a  call    cs:__imp_GetLastError
0x18000f080  mov     ebx, eax
0x18000f082  test    eax, eax
0x18000f084  jle     short loc_18000F096
0x18000f086  movzx   ebx, ax
0x18000f089  or      ebx, 80070000h
0x18000f08f  jmp     short loc_18000F096
0x18000f091  mov     ebx, 80070216h
0x18000f096  mov     rcx, rdi; pv
0x18000f099  call    cs:__imp_CoTaskMemFree
0x18000f09f  mov     eax, ebx
0x18000f0a1  mov     rbx, [rsp+0E8h+arg_8]
0x18000f0a9  add     rsp, 0C0h
0x18000f0b0  pop     r15
0x18000f0b2  pop     r14
0x18000f0b4  pop     rdi
0x18000f0b5  pop     rsi
0x18000f0b6  pop     rbp
0x18000f0b7  retn
```
