# CreateBstrArray(ushort * * *,ulong *,ushort const * *,ulong)

- ea: `0x18006dcd0`
- end: `0x18006de18`
- name: `?CreateBstrArray@@YAJPEAPEAPEAGPEAKPEAPEBGK@Z`
- size: `328`
- prototype: `__int64 __fastcall(unsigned __int16 ***, unsigned int *, const unsigned __int16 **, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007c7c`
- `0x18005d690`
- `0x18006dcd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006dde9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006dde9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006dd58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006dd58`
- `OLEAUT32!__imp_SysAllocString` at `0x18006dd99`
- `OLEAUT32!__imp_SysAllocString` at `0x18006dd99`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ddd4`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ddd4`

## pseudocode

```c
__int64 __fastcall CreateBstrArray(
        unsigned __int16 ***a1,
        unsigned int *a2,
        const unsigned __int16 **a3,
        unsigned int a4)
{
  unsigned int v8; // ebp
  unsigned int i; // edx
  int v10; // ecx
  unsigned int j; // ebx
  size_t v12; // r14
  unsigned __int16 **v13; // rax
  unsigned __int16 **v14; // rdi
  __int64 v15; // r14
  const OLECHAR *v16; // rcx
  BSTR v17; // rax
  SIZE_T v18; // rcx
  __int64 v19; // rsi
  OLECHAR *v20; // rcx
  SIZE_T cb; // [rsp+78h] [rbp+10h] BYREF

  if ( !a2 || !a1 || !a3 )
    return (unsigned int)-2147024809;
  *a1 = 0;
  v8 = 0;
  *a2 = 0;
  for ( i = 0; i < a4; v8 += v10 )
    v10 = a3[i++] != 0;
  LODWORD(cb) = 0;
  j = ULongLongToULong(8LL * v8, (unsigned int *)&cb);
  if ( (j & 0x80000000) == 0 )
  {
    v12 = (unsigned int)cb;
    v13 = (unsigned __int16 **)CoTaskMemAlloc((unsigned int)cb);
    v14 = v13;
    if ( !v13 )
      return (unsigned int)-2147024882;
    memset_0(v13, 0, v12);
    v15 = 0;
    cb = (SIZE_T)v14;
    while ( 1 )
    {
      if ( (unsigned int)v15 >= a4 )
      {
        *a2 = v8;
        *a1 = v14;
        return j;
      }
      v16 = a3[v15];
      if ( v16 )
      {
        v17 = SysAllocString(v16);
        v18 = cb;
        *(_QWORD *)cb = v17;
        if ( !v17 )
        {
          v19 = 0;
          for ( j = -2147024882; (unsigned int)v19 < v8; v19 = (unsigned int)(v19 + 1) )
          {
            v20 = v14[v19];
            if ( v20 )
              SysFreeString(v20);
          }
          CoTaskMemFree(v14);
          return j;
        }
        cb = v18 + 8;
      }
      v15 = (unsigned int)(v15 + 1);
    }
  }
  return j;
}

```

## disassembly

```asm
0x18006dcd0  push    rbx
0x18006dcd2  push    rbp
0x18006dcd3  push    rsi
0x18006dcd4  push    rdi
0x18006dcd5  push    r12
0x18006dcd7  push    r13
0x18006dcd9  push    r14
0x18006dcdb  push    r15
0x18006dcdd  sub     rsp, 28h
0x18006dce1  mov     r13d, r9d
0x18006dce4  mov     r12, r8
0x18006dce7  xor     r9d, r9d
0x18006dcea  mov     r15, rdx
0x18006dced  mov     rsi, rcx
0x18006dcf0  test    rdx, rdx
0x18006dcf3  jz      loc_18006DDFF
0x18006dcf9  test    rcx, rcx
0x18006dcfc  jz      loc_18006DDFF
0x18006dd02  test    r8, r8
0x18006dd05  jz      loc_18006DDFF
0x18006dd0b  mov     [rcx], r9
0x18006dd0e  mov     ebp, r9d
0x18006dd11  mov     [rdx], r9d
0x18006dd14  mov     edx, r9d
0x18006dd17  test    r13d, r13d
0x18006dd1a  jz      short loc_18006DD31
0x18006dd1c  mov     eax, edx
0x18006dd1e  mov     ecx, r9d
0x18006dd21  cmp     [r8+rax*8], r9
0x18006dd25  setnz   cl
0x18006dd28  inc     edx
0x18006dd2a  add     ebp, ecx
0x18006dd2c  cmp     edx, r13d
0x18006dd2f  jb      short loc_18006DD1C
0x18006dd31  mov     ecx, ebp
0x18006dd33  lea     rdx, [rsp+68h+cb]; unsigned int *
0x18006dd38  shl     rcx, 3; unsigned __int64
0x18006dd3c  mov     dword ptr [rsp+68h+cb], r9d
0x18006dd41  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18006dd46  mov     ebx, eax
0x18006dd48  test    eax, eax
0x18006dd4a  js      loc_18006DE04
0x18006dd50  mov     r14d, dword ptr [rsp+68h+cb]
0x18006dd55  mov     ecx, r14d; cb
0x18006dd58  call    cs:__imp_CoTaskMemAlloc
0x18006dd5f  nop     dword ptr [rax+rax+00h]
0x18006dd64  mov     rdi, rax
0x18006dd67  test    rax, rax
0x18006dd6a  jnz     short loc_18006DD76
0x18006dd6c  mov     ebx, 8007000Eh
0x18006dd71  jmp     loc_18006DE04
0x18006dd76  mov     r8, r14; Size
0x18006dd79  xor     edx, edx; Val
0x18006dd7b  mov     rcx, rdi; void *
0x18006dd7e  call    memset_0
0x18006dd83  xor     r14d, r14d
0x18006dd86  mov     [rsp+68h+cb], rdi
0x18006dd8b  cmp     r14d, r13d
0x18006dd8e  jnb     short loc_18006DDF7
0x18006dd90  mov     rcx, [r12+r14*8]; psz
0x18006dd94  test    rcx, rcx
0x18006dd97  jz      short loc_18006DDBB
0x18006dd99  call    cs:__imp_SysAllocString
0x18006dda0  nop     dword ptr [rax+rax+00h]
0x18006dda5  mov     rcx, [rsp+68h+cb]
0x18006ddaa  mov     [rcx], rax
0x18006ddad  test    rax, rax
0x18006ddb0  jz      short loc_18006DDC0
0x18006ddb2  add     rcx, 8
0x18006ddb6  mov     [rsp+68h+cb], rcx
0x18006ddbb  inc     r14d
0x18006ddbe  jmp     short loc_18006DD8B
0x18006ddc0  xor     esi, esi
0x18006ddc2  mov     ebx, 8007000Eh
0x18006ddc7  test    ebp, ebp
0x18006ddc9  jz      short loc_18006DDE6
0x18006ddcb  mov     rcx, [rdi+rsi*8]; bstrString
0x18006ddcf  test    rcx, rcx
0x18006ddd2  jz      short loc_18006DDE0
0x18006ddd4  call    cs:__imp_SysFreeString
0x18006dddb  nop     dword ptr [rax+rax+00h]
0x18006dde0  inc     esi
0x18006dde2  cmp     esi, ebp
0x18006dde4  jb      short loc_18006DDCB
0x18006dde6  mov     rcx, rdi; pv
0x18006dde9  call    cs:__imp_CoTaskMemFree
0x18006ddf0  nop     dword ptr [rax+rax+00h]
0x18006ddf5  jmp     short loc_18006DE04
0x18006ddf7  mov     [r15], ebp
0x18006ddfa  mov     [rsi], rdi
0x18006ddfd  jmp     short loc_18006DE04
0x18006ddff  mov     ebx, 80070057h
0x18006de04  mov     eax, ebx
0x18006de06  add     rsp, 28h
0x18006de0a  pop     r15
0x18006de0c  pop     r14
0x18006de0e  pop     r13
0x18006de10  pop     r12
0x18006de12  pop     rdi
0x18006de13  pop     rsi
0x18006de14  pop     rbp
0x18006de15  pop     rbx
0x18006de16  retn
```
