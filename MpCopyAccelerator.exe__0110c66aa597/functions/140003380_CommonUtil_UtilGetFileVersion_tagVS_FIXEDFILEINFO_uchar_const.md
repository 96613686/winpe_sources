# CommonUtil::UtilGetFileVersion(tagVS_FIXEDFILEINFO *,uchar const *)

- ea: `0x140003380`
- end: `0x140003412`
- name: `?UtilGetFileVersion@CommonUtil@@YAJPEAUtagVS_FIXEDFILEINFO@@PEBE@Z`
- size: `146`
- prototype: `int(CommonUtil *__hidden this, struct tagVS_FIXEDFILEINFO *, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003414`

## callees

- `0x140003380`
- `0x14000567c`
- `0x140005c20`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetFileVersion(
        CommonUtil *this,
        struct tagVS_FIXEDFILEINFO *a2,
        const unsigned __int8 *a3)
{
  __int64 result; // rax
  _OWORD *v5; // rax
  wchar_t v6[4]; // [rsp+20h] [rbp-28h] BYREF
  void *v7; // [rsp+28h] [rbp-20h] BYREF

  LODWORD(v7) = 0;
  result = CommonUtil::UtilVerQueryValueW((CommonUtil *)a2, L"\\", v6, &v7, 0);
  if ( (int)result >= 0 )
  {
    if ( (unsigned int)v7 >= 0x34 )
    {
      v5 = *(_OWORD **)v6;
      *(_OWORD *)this = **(_OWORD **)v6;
      *((_OWORD *)this + 1) = v5[1];
      *((_OWORD *)this + 2) = v5[2];
      *((_DWORD *)this + 12) = *((_DWORD *)v5 + 12);
      return 0;
    }
    else
    {
      return 2147549183LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003380  push    rbx
0x140003382  sub     rsp, 40h
0x140003386  mov     rax, cs:__security_cookie
0x14000338d  xor     rax, rsp
0x140003390  mov     [rsp+48h+var_18], rax
0x140003395  mov     rax, rdx
0x140003398  mov     dword ptr [rsp+48h+var_20], 0
0x1400033a0  mov     rbx, rcx
0x1400033a3  mov     qword ptr [rsp+48h+var_28], 0; unsigned int *
0x1400033ac  mov     rcx, rax; this
0x1400033af  lea     r9, [rsp+48h+var_20]; void **
0x1400033b4  lea     r8, [rsp+48h+var_28]; wchar_t *
0x1400033b9  lea     rdx, asc_140034BB0; "\\"
0x1400033c0  call    ?UtilVerQueryValueW@CommonUtil@@YAJPEBXPEB_WPEAPEAXPEAI@Z; CommonUtil::UtilVerQueryValueW(void const *,wchar_t const *,void * *,uint *)
0x1400033c5  mov     edx, eax
0x1400033c7  shr     edx, 1Fh
0x1400033ca  test    dl, dl
0x1400033cc  jnz     short loc_1400033FF
0x1400033ce  cmp     dword ptr [rsp+48h+var_20], 34h ; '4'
0x1400033d3  jnb     short loc_1400033DC
0x1400033d5  mov     eax, 8000FFFFh
0x1400033da  jmp     short loc_1400033FF
0x1400033dc  mov     rax, qword ptr [rsp+48h+var_28]
0x1400033e1  movups  xmm0, xmmword ptr [rax]
0x1400033e4  movups  xmmword ptr [rbx], xmm0
0x1400033e7  movups  xmm1, xmmword ptr [rax+10h]
0x1400033eb  movups  xmmword ptr [rbx+10h], xmm1
0x1400033ef  movups  xmm0, xmmword ptr [rax+20h]
0x1400033f3  movups  xmmword ptr [rbx+20h], xmm0
0x1400033f7  mov     eax, [rax+30h]
0x1400033fa  mov     [rbx+30h], eax
0x1400033fd  xor     eax, eax
0x1400033ff  mov     rcx, [rsp+48h+var_18]
0x140003404  xor     rcx, rsp; StackCookie
0x140003407  call    __security_check_cookie
0x14000340c  add     rsp, 40h
0x140003410  pop     rbx
0x140003411  retn
```
