# StartAddress

- ea: `0x1800ef5e0`
- end: `0x1800ef8ce`
- name: `StartAddress`
- size: `750`
- prototype: `unsigned __int64 __fastcall(_onexit_table_t *lpThreadParameter)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x1800048f0`
- `0x18001916c`
- `0x180023c04`
- `0x180025918`
- `0x180025a94`
- `0x180028810`
- `0x1800322b0`
- `0x18003efbc`
- `0x1800ee1e4`
- `0x1800ee6d8`
- `0x1800ef128`
- `0x1800ef5e0`
- `0x180135010`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800ef7bd`
- `KERNEL32!Sleep` at `0x1800ef7bd`
- `ole32!CoUninitialize` at `0x1800ef8a4`
- `ole32!CoUninitialize` at `0x1800ef8a4`
- `ole32!CoCreateInstance` at `0x1800ef666`
- `ole32!CoCreateInstance` at `0x1800ef666`
- `ole32!CoInitializeEx` at `0x1800ef632`
- `ole32!CoInitializeEx` at `0x1800ef632`

## pseudocode

```c
unsigned __int64 __fastcall StartAddress(_onexit_table_t *lpThreadParameter)
{
  __int64 v1; // r8
  HRESULT v2; // ebx
  HRESULT v3; // edi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rax
  _QWORD *v7; // rdi
  __int128 *v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // edi
  _QWORD *v13; // rdi
  __int128 *v14; // r9
  __int128 v16; // [rsp+30h] [rbp-89h] BYREF
  __int128 v17; // [rsp+40h] [rbp-79h]
  __int64 v18; // [rsp+50h] [rbp-69h] BYREF
  __int64 v19; // [rsp+58h] [rbp-61h] BYREF
  __int128 v20; // [rsp+60h] [rbp-59h] BYREF
  __int128 v21; // [rsp+70h] [rbp-49h]
  HRESULT v22; // [rsp+80h] [rbp-39h]
  _BYTE v23[4]; // [rsp+84h] [rbp-35h] BYREF
  unsigned int v24; // [rsp+88h] [rbp-31h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp-29h] BYREF
  __int64 v26; // [rsp+98h] [rbp-21h] BYREF
  _OWORD v27[2]; // [rsp+A0h] [rbp-19h] BYREF
  _BYTE v28[32]; // [rsp+C0h] [rbp+7h] BYREF

  memset(v27, 0, sizeof(v27));
  v1 = -1;
  do
    ++v1;
  while ( *((_WORD *)&lpThreadParameter->_first + v1) );
  sub_18001916C(v27, lpThreadParameter);
  v2 = CoInitializeEx(0, 2u);
  v22 = v2;
  if ( v2 < 0 )
  {
    v3 = v2;
  }
  else
  {
    ppv = 0;
    v3 = CoCreateInstance(&stru_180166350, 0, 1u, &stru_180166340, &ppv);
    if ( v3 >= 0 )
    {
      v3 = sub_1800EF128(&ppv, v27);
      if ( v3 >= 0 )
      {
        v26 = 0;
        v23[0] = 0;
        v6 = sub_180025918(v5, v4);
        if ( (unsigned __int8)sub_180023C04(v6 + 21200, v23, &v26) )
        {
          if ( v23[0] )
          {
            if ( (*(_BYTE *)(*(_QWORD *)sub_180025A94() + 32LL) & 8) != 0 )
            {
              v7 = (_QWORD *)sub_180025A94();
              v16 = 0;
              v17 = 0;
              sub_18001916C(&v16, L"DesktopWallpaper:Set: Detected first time logon.", 48);
              v20 = 0;
              v21 = 0;
              sub_18001916C(&v20, L"LocalStore", 10);
              v8 = &v16;
              if ( *((_QWORD *)&v17 + 1) > 7u )
                v8 = (__int128 *)v16;
              sub_18003EFBC(*v7, 8, &v20, v8);
              sub_180028810(&v20);
              sub_180028810(&v16);
            }
            v19 = 0;
            v18 = 0;
            sub_1800EE1E4(v28, &v19, &v18);
            v24 = 10;
            v11 = sub_180025918(v10, v9);
            sub_1800322B0(v11 + 16528, &v24, &v26);
            v12 = 0;
            if ( v24 )
            {
              while ( !(unsigned __int8)sub_1800EE6D8(v28, v19, v18) )
              {
                Sleep(0x3E8u);
                if ( ++v12 >= v24 )
                  goto LABEL_20;
              }
              if ( (*(_BYTE *)(*(_QWORD *)sub_180025A94() + 32LL) & 8) != 0 )
              {
                v13 = (_QWORD *)sub_180025A94();
                v16 = 0;
                v17 = 0;
                sub_18001916C(&v16, L"DesktopWallpaper:Set: Wallpaper has changed. Setting back.", 58);
                v20 = 0;
                v21 = 0;
                sub_18001916C(&v20, L"LocalStore", 10);
                v14 = &v16;
                if ( *((_QWORD *)&v17 + 1) > 7u )
                  v14 = (__int128 *)v16;
                sub_18003EFBC(*v13, 8, &v20, v14);
                sub_180028810(&v20);
                sub_180028810(&v16);
              }
            }
LABEL_20:
            v3 = sub_1800EF128(&ppv, v27);
            sub_180028810(v28);
          }
        }
      }
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  if ( v2 >= 0 )
    CoUninitialize();
  sub_180028810(v27);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800ef5e0  push    rbp
0x1800ef5e2  push    rbx
0x1800ef5e3  push    rsi
0x1800ef5e4  push    rdi
0x1800ef5e5  lea     rbp, [rsp-3Fh]
0x1800ef5ea  sub     rsp, 0F8h
0x1800ef5f1  mov     rax, cs:__security_cookie
0x1800ef5f8  xor     rax, rsp
0x1800ef5fb  mov     [rbp+57h+var_30], rax
0x1800ef5ff  xorps   xmm0, xmm0
0x1800ef602  movups  [rbp+57h+var_70], xmm0
0x1800ef606  xorps   xmm1, xmm1
0x1800ef609  movdqu  [rbp+57h+var_60], xmm1
0x1800ef60e  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800ef612  xor     esi, esi
0x1800ef614  inc     r8
0x1800ef617  cmp     [rcx+r8*2], si
0x1800ef61c  jnz     short loc_1800EF614
0x1800ef61e  mov     rdx, rcx
0x1800ef621  lea     rcx, [rbp+57h+var_70]
0x1800ef625  call    sub_18001916C
0x1800ef62a  nop
0x1800ef62b  mov     edx, 2; dwCoInit
0x1800ef630  xor     ecx, ecx; pvReserved
0x1800ef632  call    cs:CoInitializeEx
0x1800ef638  mov     ebx, eax
0x1800ef63a  mov     [rbp+57h+var_90], eax
0x1800ef63d  test    eax, eax
0x1800ef63f  js      loc_1800EF89E
0x1800ef645  mov     [rbp+57h+var_80], rsi
0x1800ef649  lea     rax, [rbp+57h+var_80]
0x1800ef64d  mov     [rsp+110h+ppv], rax; ppv
0x1800ef652  lea     r9, stru_180166340; riid
0x1800ef659  xor     edx, edx; pUnkOuter
0x1800ef65b  lea     r8d, [rdx+1]; dwClsContext
0x1800ef65f  lea     rcx, stru_180166350; rclsid
0x1800ef666  call    cs:CoCreateInstance
0x1800ef66c  mov     edi, eax
0x1800ef66e  test    eax, eax
0x1800ef670  js      loc_1800EF886
0x1800ef676  lea     rdx, [rbp+57h+var_70]
0x1800ef67a  lea     rcx, [rbp+57h+var_80]
0x1800ef67e  call    sub_1800EF128
0x1800ef683  mov     edi, eax
0x1800ef685  test    eax, eax
0x1800ef687  js      loc_1800EF886
0x1800ef68d  mov     [rbp+57h+var_78], rsi
0x1800ef691  mov     [rbp+57h+var_8C], sil
0x1800ef695  call    sub_180025918
0x1800ef69a  lea     rcx, [rax+52D0h]
0x1800ef6a1  lea     r8, [rbp+57h+var_78]
0x1800ef6a5  lea     rdx, [rbp+57h+var_8C]
0x1800ef6a9  call    sub_180023C04
0x1800ef6ae  test    al, al
0x1800ef6b0  jz      loc_1800EF886
0x1800ef6b6  cmp     [rbp+57h+var_8C], sil
0x1800ef6ba  jz      loc_1800EF886
0x1800ef6c0  call    sub_180025A94
0x1800ef6c5  mov     rcx, [rax]
0x1800ef6c8  test    byte ptr [rcx+20h], 8
0x1800ef6cc  jbe     loc_1800EF75E
0x1800ef6d2  call    sub_180025A94
0x1800ef6d7  mov     rdi, rax
0x1800ef6da  xorps   xmm0, xmm0
0x1800ef6dd  movups  [rsp+110h+var_E0], xmm0
0x1800ef6e2  xorps   xmm1, xmm1
0x1800ef6e5  movdqu  [rbp+57h+var_D0], xmm1
0x1800ef6ea  mov     r8d, 30h ; '0'
0x1800ef6f0  lea     rdx, aDesktopwallpap_14; "DesktopWallpaper:Set: Detected first ti"...
0x1800ef6f7  lea     rcx, [rsp+110h+var_E0]
0x1800ef6fc  call    sub_18001916C
0x1800ef701  nop
0x1800ef702  xorps   xmm0, xmm0
0x1800ef705  movups  [rbp+57h+var_B0], xmm0
0x1800ef709  xorps   xmm1, xmm1
0x1800ef70c  movdqu  [rbp+57h+var_A0], xmm1
0x1800ef711  mov     r8d, 0Ah
0x1800ef717  lea     rdx, aLocalstore; "LocalStore"
0x1800ef71e  lea     rcx, [rbp+57h+var_B0]
0x1800ef722  call    sub_18001916C
0x1800ef727  nop
0x1800ef728  lea     r9, [rsp+110h+var_E0]
0x1800ef72d  cmp     qword ptr [rbp+57h+var_D0+8], 7
0x1800ef732  cmova   r9, qword ptr [rsp+110h+var_E0]
0x1800ef738  lea     r8, [rbp+57h+var_B0]
0x1800ef73c  mov     edx, 8
0x1800ef741  mov     rcx, [rdi]
0x1800ef744  call    sub_18003EFBC
0x1800ef749  nop
0x1800ef74a  lea     rcx, [rbp+57h+var_B0]
0x1800ef74e  call    sub_180028810
0x1800ef753  nop
0x1800ef754  lea     rcx, [rsp+110h+var_E0]
0x1800ef759  call    sub_180028810
0x1800ef75e  mov     [rbp+57h+var_B8], rsi
0x1800ef762  mov     [rbp+57h+var_C0], rsi
0x1800ef766  lea     r8, [rbp+57h+var_C0]
0x1800ef76a  lea     rdx, [rbp+57h+var_B8]
0x1800ef76e  lea     rcx, [rbp+57h+var_50]
0x1800ef772  call    sub_1800EE1E4
0x1800ef777  nop
0x1800ef778  mov     [rbp+57h+var_88], 0Ah
0x1800ef77f  call    sub_180025918
0x1800ef784  lea     rcx, [rax+4090h]
0x1800ef78b  lea     r8, [rbp+57h+var_78]
0x1800ef78f  lea     rdx, [rbp+57h+var_88]
0x1800ef793  call    sub_1800322B0
0x1800ef798  mov     edi, esi
0x1800ef79a  cmp     [rbp+57h+var_88], esi
0x1800ef79d  jbe     loc_1800EF86D
0x1800ef7a3  mov     r8, [rbp+57h+var_C0]
0x1800ef7a7  mov     rdx, [rbp+57h+var_B8]
0x1800ef7ab  lea     rcx, [rbp+57h+var_50]
0x1800ef7af  call    sub_1800EE6D8
0x1800ef7b4  test    al, al
0x1800ef7b6  jnz     short loc_1800EF7CF
0x1800ef7b8  mov     ecx, 3E8h; dwMilliseconds
0x1800ef7bd  call    cs:Sleep
0x1800ef7c3  inc     edi
0x1800ef7c5  cmp     edi, [rbp+57h+var_88]
0x1800ef7c8  jb      short loc_1800EF7A3
0x1800ef7ca  jmp     loc_1800EF86D
0x1800ef7cf  call    sub_180025A94
0x1800ef7d4  mov     rcx, [rax]
0x1800ef7d7  test    byte ptr [rcx+20h], 8
0x1800ef7db  jbe     loc_1800EF86D
0x1800ef7e1  call    sub_180025A94
0x1800ef7e6  mov     rdi, rax
0x1800ef7e9  xorps   xmm0, xmm0
0x1800ef7ec  movups  [rsp+110h+var_E0], xmm0
0x1800ef7f1  xorps   xmm1, xmm1
0x1800ef7f4  movdqu  [rbp+57h+var_D0], xmm1
0x1800ef7f9  mov     r8d, 3Ah ; ':'
0x1800ef7ff  lea     rdx, aDesktopwallpap_15; "DesktopWallpaper:Set: Wallpaper has cha"...
0x1800ef806  lea     rcx, [rsp+110h+var_E0]
0x1800ef80b  call    sub_18001916C
0x1800ef810  nop
0x1800ef811  xorps   xmm0, xmm0
0x1800ef814  movups  [rbp+57h+var_B0], xmm0
0x1800ef818  xorps   xmm1, xmm1
0x1800ef81b  movdqu  [rbp+57h+var_A0], xmm1
0x1800ef820  mov     r8d, 0Ah
0x1800ef826  lea     rdx, aLocalstore; "LocalStore"
0x1800ef82d  lea     rcx, [rbp+57h+var_B0]
0x1800ef831  call    sub_18001916C
0x1800ef836  nop
0x1800ef837  lea     r9, [rsp+110h+var_E0]
0x1800ef83c  cmp     qword ptr [rbp+57h+var_D0+8], 7
0x1800ef841  cmova   r9, qword ptr [rsp+110h+var_E0]
0x1800ef847  lea     r8, [rbp+57h+var_B0]
0x1800ef84b  mov     edx, 8
0x1800ef850  mov     rcx, [rdi]
0x1800ef853  call    sub_18003EFBC
0x1800ef858  nop
0x1800ef859  lea     rcx, [rbp+57h+var_B0]
0x1800ef85d  call    sub_180028810
0x1800ef862  nop
0x1800ef863  lea     rcx, [rsp+110h+var_E0]
0x1800ef868  call    sub_180028810
0x1800ef86d  lea     rdx, [rbp+57h+var_70]
0x1800ef871  lea     rcx, [rbp+57h+var_80]
0x1800ef875  call    sub_1800EF128
0x1800ef87a  mov     edi, eax
0x1800ef87c  lea     rcx, [rbp+57h+var_50]
0x1800ef880  call    sub_180028810
0x1800ef885  nop
0x1800ef886  mov     rcx, [rbp+57h+var_80]
0x1800ef88a  test    rcx, rcx
0x1800ef88d  jz      short loc_1800EF89C
0x1800ef88f  mov     rax, [rcx]
0x1800ef892  mov     rax, [rax+10h]
0x1800ef896  call    j__guard_dispatch_icall
0x1800ef89b  nop
0x1800ef89c  jmp     short loc_1800EF8A0
0x1800ef89e  mov     edi, ebx
0x1800ef8a0  test    ebx, ebx
0x1800ef8a2  js      short loc_1800EF8AB
0x1800ef8a4  call    cs:CoUninitialize
0x1800ef8aa  nop
0x1800ef8ab  lea     rcx, [rbp+57h+var_70]
0x1800ef8af  call    sub_180028810
0x1800ef8b4  mov     eax, edi
0x1800ef8b6  mov     rcx, [rbp+57h+var_30]
0x1800ef8ba  xor     rcx, rsp; StackCookie
0x1800ef8bd  call    __security_check_cookie
0x1800ef8c2  add     rsp, 0F8h
0x1800ef8c9  pop     rdi
0x1800ef8ca  pop     rsi
0x1800ef8cb  pop     rbx
0x1800ef8cc  pop     rbp
0x1800ef8cd  retn
```
