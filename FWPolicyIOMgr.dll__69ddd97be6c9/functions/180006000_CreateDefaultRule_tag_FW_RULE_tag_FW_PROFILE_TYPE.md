# CreateDefaultRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)

- ea: `0x180006000`
- end: `0x18000621e`
- name: `?CreateDefaultRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(void **, int)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005e40`
- `0x180005ef0`
- `0x180020990`
- `0x180020a90`
- `0x180020d60`

## callees

- `0x1800042c4`
- `0x180006000`
- `0x180006f50`
- `0x18001f650`
- `0x18001ffd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180006103`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180006103`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006123`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006123`
- `fwbase!FwAlloc` at `0x180006041`
- `fwbase!FwAlloc` at `0x180006041`
- `fwbase!FwStringCopy` at `0x18000613d`
- `fwbase!FwStringCopy` at `0x18000613d`

## pseudocode

```c
__int64 __fastcall CreateDefaultRule(void **a1, int a2)
{
  void *v4; // rax
  HRESULT v5; // ebx
  LPCOLESTR v6; // rcx
  __int64 v7; // rdx
  GUID pguid; // [rsp+20h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+30h] [rbp-68h] BYREF

  pguid = 0;
  memset_0(sz, 0, 0x4Eu);
  v4 = (void *)FwAlloc(504);
  *a1 = v4;
  if ( !v4 )
  {
    v5 = -2147024882;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_10;
    v7 = 156;
    goto LABEL_8;
  }
  memset_0(v4, 0, 0x1F8u);
  *((_WORD *)*a1 + 4) = 545;
  *((_WORD *)*a1 + 146) |= 1u;
  *((_DWORD *)*a1 + 72) = 0;
  *((_DWORD *)*a1 + 11) = 0;
  *((_WORD *)*a1 + 24) = 256;
  *((_DWORD *)*a1 + 10) = a2;
  *((_QWORD *)*a1 + 34) = 0;
  *((_QWORD *)*a1 + 35) = 0;
  *((_QWORD *)*a1 + 37) = 0;
  *((_QWORD *)*a1 + 38) = 0;
  *((_QWORD *)*a1 + 39) = 0;
  *((_QWORD *)*a1 + 43) = 0;
  *((_DWORD *)*a1 + 84) = 0x10000;
  v5 = CoCreateGuid(&pguid);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_10;
    v7 = 157;
    goto LABEL_8;
  }
  if ( !StringFromGUID2(&pguid, sz, 39) )
  {
    v5 = -2147024774;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_10;
    v7 = 158;
    goto LABEL_8;
  }
  v5 = FwStringCopy(sz, (char *)*a1 + 16);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_10;
    v7 = 159;
LABEL_8:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v5);
LABEL_10:
    FwFreeWFRule(*a1);
    *a1 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180006000  mov     [rsp+arg_8], rbx
0x180006005  push    rdi
0x180006006  sub     rsp, 90h
0x18000600d  mov     rax, cs:__security_cookie
0x180006014  xor     rax, rsp
0x180006017  mov     [rsp+98h+var_18], rax
0x18000601f  mov     ebx, edx
0x180006021  mov     rdi, rcx
0x180006024  xor     edx, edx; Val
0x180006026  lea     rcx, [rsp+98h+sz]; void *
0x18000602b  xorps   xmm0, xmm0
0x18000602e  movups  xmmword ptr [rsp+98h+pguid.Data1], xmm0
0x180006033  lea     r8d, [rdx+4Eh]; Size
0x180006037  call    memset_0
0x18000603c  mov     ecx, 1F8h
0x180006041  call    cs:__imp_FwAlloc
0x180006047  mov     [rdi], rax
0x18000604a  test    rax, rax
0x18000604d  jz      loc_18000617C
0x180006053  xor     edx, edx; Val
0x180006055  mov     r8d, 1F8h; Size
0x18000605b  mov     rcx, rax; void *
0x18000605e  call    memset_0
0x180006063  mov     rax, [rdi]
0x180006066  lea     rcx, [rsp+98h+pguid]; pguid
0x18000606b  mov     word ptr [rax+8], 221h
0x180006071  mov     rax, [rdi]
0x180006074  or      word ptr [rax+124h], 1
0x18000607c  mov     rax, [rdi]
0x18000607f  mov     dword ptr [rax+120h], 0
0x180006089  mov     rax, [rdi]
0x18000608c  mov     dword ptr [rax+2Ch], 0
0x180006093  mov     rax, [rdi]
0x180006096  mov     word ptr [rax+30h], 100h
0x18000609c  mov     rax, [rdi]
0x18000609f  mov     [rax+28h], ebx
0x1800060a2  mov     rax, [rdi]
0x1800060a5  mov     qword ptr [rax+110h], 0
0x1800060b0  mov     rax, [rdi]
0x1800060b3  mov     qword ptr [rax+118h], 0
0x1800060be  mov     rax, [rdi]
0x1800060c1  mov     qword ptr [rax+128h], 0
0x1800060cc  mov     rax, [rdi]
0x1800060cf  mov     qword ptr [rax+130h], 0
0x1800060da  mov     rax, [rdi]
0x1800060dd  mov     qword ptr [rax+138h], 0
0x1800060e8  mov     rax, [rdi]
0x1800060eb  mov     qword ptr [rax+158h], 0
0x1800060f6  mov     rax, [rdi]
0x1800060f9  mov     dword ptr [rax+150h], 10000h
0x180006103  call    cs:__imp_CoCreateGuid
0x180006109  mov     ebx, eax
0x18000610b  test    eax, eax
0x18000610d  js      loc_1800061D3
0x180006113  mov     r8d, 27h ; '''; cchMax
0x180006119  lea     rdx, [rsp+98h+sz]; lpsz
0x18000611e  lea     rcx, [rsp+98h+pguid]; rguid
0x180006123  call    cs:__imp_StringFromGUID2
0x180006129  test    eax, eax
0x18000612b  jz      loc_1800061F6
0x180006131  mov     rdx, [rdi]
0x180006134  lea     rcx, [rsp+98h+sz]
0x180006139  add     rdx, 10h
0x18000613d  call    cs:__imp_FwStringCopy
0x180006143  mov     ebx, eax
0x180006145  test    eax, eax
0x180006147  jns     short loc_1800061A3
0x180006149  mov     rcx, cs:WPP_GLOBAL_Control
0x180006150  lea     rax, WPP_GLOBAL_Control
0x180006157  cmp     rcx, rax
0x18000615a  jz      short loc_180006194
0x18000615c  test    byte ptr [rcx+1Ch], 1
0x180006160  jz      short loc_180006194
0x180006162  mov     edx, 9Fh
0x180006167  mov     rcx, [rcx+10h]
0x18000616b  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180006172  mov     r9d, ebx
0x180006175  call    WPP_SF_d
0x18000617a  jmp     short loc_180006194
0x18000617c  mov     ebx, 8007000Eh
0x180006181  mov     rcx, cs:WPP_GLOBAL_Control
0x180006188  lea     rax, WPP_GLOBAL_Control
0x18000618f  cmp     rcx, rax
0x180006192  jnz     short loc_1800061C6
0x180006194  mov     rcx, [rdi]; void *
0x180006197  call    FwFreeWFRule
0x18000619c  mov     qword ptr [rdi], 0
0x1800061a3  mov     eax, ebx
0x1800061a5  mov     rcx, [rsp+98h+var_18]
0x1800061ad  xor     rcx, rsp; StackCookie
0x1800061b0  call    __security_check_cookie
0x1800061b5  mov     rbx, [rsp+98h+arg_8]
0x1800061bd  add     rsp, 90h
0x1800061c4  pop     rdi
0x1800061c5  retn
0x1800061c6  test    byte ptr [rcx+1Ch], 1
0x1800061ca  jz      short loc_180006194
0x1800061cc  mov     edx, 9Ch
0x1800061d1  jmp     short loc_180006167
0x1800061d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061da  lea     rax, WPP_GLOBAL_Control
0x1800061e1  cmp     rcx, rax
0x1800061e4  jz      short loc_180006194
0x1800061e6  test    byte ptr [rcx+1Ch], 1
0x1800061ea  jz      short loc_180006194
0x1800061ec  mov     edx, 9Dh
0x1800061f1  jmp     loc_180006167
0x1800061f6  mov     ebx, 8007007Ah
0x1800061fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006202  lea     rax, WPP_GLOBAL_Control
0x180006209  cmp     rcx, rax
0x18000620c  jz      short loc_180006194
0x18000620e  test    byte ptr [rcx+1Ch], 1
0x180006212  jz      short loc_180006194
0x180006214  mov     edx, 9Eh
0x180006219  jmp     loc_180006167
```
