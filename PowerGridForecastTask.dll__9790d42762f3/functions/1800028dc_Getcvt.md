# _Getcvt

- ea: `0x1800028dc`
- end: `0x180002977`
- name: `_Getcvt`
- size: `155`
- prototype: `_Cvtvec *__cdecl(_Cvtvec *__return_ptr __struct_ptr retstr)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x180005a24`
- `0x180008484`
- `0x18000915c`
- `0x180009374`
- `0x18000c640`
- `0x18000c958`
- `0x180011d18`
- `0x180011ec0`
- `0x180012068`
- `0x180012268`
- `0x180012c38`
- `0x180013898`
- `0x18001cb44`
- `0x18001f2b4`
- `0x18003158c`
- `0x180033e38`

## callees

- `0x1800028dc`
- `0x1800086f8`

## import_xrefs

- `msvcrt!_ismbblead` at `0x18000293e`
- `msvcrt!_ismbblead` at `0x18000293e`
- `msvcrt!___lc_codepage_func` at `0x180002902`
- `msvcrt!___lc_codepage_func` at `0x180002902`
- `msvcrt!___lc_handle_func` at `0x1800028f7`
- `msvcrt!___lc_handle_func` at `0x1800028f7`
- `msvcrt!___mb_cur_max_func` at `0x18000290b`
- `msvcrt!___mb_cur_max_func` at `0x18000290b`
- `msvcrt!free` at `0x18000292f`
- `msvcrt!free` at `0x18000292f`

## pseudocode

```c
_Cvtvec *__cdecl Getcvt(_Cvtvec *__return_ptr retstr)
{
  void *LocaleName; // rbx
  signed int i; // ebx

  *(_OWORD *)&retstr->_Page = 0;
  *(_OWORD *)&retstr->_Isleadbyte[4] = 0;
  *(_OWORD *)&retstr->_Isleadbyte[20] = 0;
  retstr->_Page = *(_DWORD *)(___lc_handle_func() + 8);
  retstr->_Mbcurmax = ___lc_codepage_func();
  retstr->_Isclocale = ___mb_cur_max_func();
  LocaleName = (void *)GetLocaleName(2);
  *(_DWORD *)retstr->_Isleadbyte = LocaleName == 0;
  free(LocaleName);
  if ( LocaleName )
  {
    for ( i = 0; i < 256; ++i )
    {
      if ( _ismbblead(i) )
        retstr->_Isleadbyte[((unsigned __int64)(unsigned int)i >> 3) + 4] |= 1 << (i & 7);
    }
  }
  return retstr;
}

```

## disassembly

```asm
0x1800028dc  mov     [rsp+arg_0], rbx
0x1800028e1  push    rdi
0x1800028e2  sub     rsp, 20h
0x1800028e6  xorps   xmm0, xmm0
0x1800028e9  mov     rdi, rcx
0x1800028ec  movups  xmmword ptr [rcx], xmm0
0x1800028ef  movups  xmmword ptr [rcx+10h], xmm0
0x1800028f3  movups  xmmword ptr [rcx+20h], xmm0
0x1800028f7  call    cs:__imp____lc_handle_func
0x1800028fd  mov     edx, [rax+8]
0x180002900  mov     [rdi], edx
0x180002902  call    cs:__imp____lc_codepage_func
0x180002908  mov     [rdi+4], eax
0x18000290b  call    cs:__imp____mb_cur_max_func
0x180002911  mov     ecx, 2
0x180002916  mov     [rdi+8], eax
0x180002919  call    _GetLocaleName
0x18000291e  xor     ecx, ecx
0x180002920  mov     rbx, rax
0x180002923  test    rax, rax
0x180002926  setz    cl
0x180002929  mov     [rdi+0Ch], ecx
0x18000292c  mov     rcx, rax; Block
0x18000292f  call    cs:__imp_free
0x180002935  test    rbx, rbx
0x180002938  jz      short loc_180002969
0x18000293a  xor     ebx, ebx
0x18000293c  mov     ecx, ebx; Ch
0x18000293e  call    cs:__imp__ismbblead
0x180002944  test    eax, eax
0x180002946  jz      short loc_18000295F
0x180002948  mov     edx, ebx
0x18000294a  mov     eax, ebx
0x18000294c  shr     rdx, 3
0x180002950  and     eax, 7
0x180002953  movzx   ecx, byte ptr [rdx+rdi+10h]
0x180002958  bts     ecx, eax
0x18000295b  mov     [rdx+rdi+10h], cl
0x18000295f  inc     ebx
0x180002961  cmp     ebx, 100h
0x180002967  jl      short loc_18000293C
0x180002969  mov     rbx, [rsp+28h+arg_0]
0x18000296e  mov     rax, rdi
0x180002971  add     rsp, 20h
0x180002975  pop     rdi
0x180002976  retn
```
