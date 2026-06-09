# Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>::Next(ulong,ushort * *,ulong *)

- ea: `0x14000ba60`
- end: `0x14000bb54`
- name: `?Next@?$IEnumOnOwnedSTLImpl@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Windows@@UEAAJKPEAPEAGPEAK@Z`
- size: `244`
- prototype: `__int64 __fastcall(__int64, unsigned int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x14000ba60`
- `0x14000f170`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bb14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bb14`

## pseudocode

```c
__int64 __fastcall Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>>::Next(
        __int64 a1,
        unsigned int a2,
        void **a3,
        unsigned int *a4)
{
  void **v4; // rdi
  unsigned int v8; // ebp
  int v9; // r15d
  void **v10; // rsi
  __int64 *v11; // rbx
  _BYTE *v12; // rcx
  __int64 *v13; // rdx
  __int64 *i; // rax
  void *v15; // rcx

  v4 = a3;
  if ( a4 )
    *a4 = 0;
  v8 = 0;
  v9 = 0;
  v10 = a3;
  v11 = *(__int64 **)(a1 + 24);
  while ( v11 != *(__int64 **)(a1 + 8) && v8 < a2 )
  {
    v9 = Windows::CopyFromPairWstringToLpolestr::copy(v10, (__int64)(v11 + 4));
    if ( v9 < 0 )
    {
      while ( v4 < v10 )
      {
        v15 = *v4++;
        CoTaskMemFree(v15);
      }
      goto LABEL_26;
    }
    ++v10;
    if ( !*((_BYTE *)v11 + 25) )
    {
      v12 = (_BYTE *)v11[2];
      if ( v12[25] )
      {
        for ( i = (__int64 *)v11[1]; !*((_BYTE *)i + 25) && v11 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v11 = i;
        v11 = i;
      }
      else
      {
        v13 = *(__int64 **)v12;
        if ( *(_BYTE *)(*(_QWORD *)v12 + 25LL) )
        {
          v11 = (__int64 *)v11[2];
        }
        else
        {
          do
          {
            v11 = v13;
            v13 = (__int64 *)*v13;
          }
          while ( !*((_BYTE *)v13 + 25) );
        }
      }
    }
    ++v8;
  }
  if ( a4 )
    *a4 = v8;
  if ( v8 < a2 )
  {
    *v10 = 0;
    v9 = 1;
  }
LABEL_26:
  *(_QWORD *)(a1 + 24) = v11;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000ba60  push    rbx
0x14000ba62  push    rbp
0x14000ba63  push    rsi
0x14000ba64  push    rdi
0x14000ba65  push    r12
0x14000ba67  push    r13
0x14000ba69  push    r14
0x14000ba6b  push    r15
0x14000ba6d  sub     rsp, 28h
0x14000ba71  mov     rdi, r8
0x14000ba74  mov     r14, r9
0x14000ba77  xor     r8d, r8d
0x14000ba7a  mov     r12d, edx
0x14000ba7d  mov     r13, rcx
0x14000ba80  test    r9, r9
0x14000ba83  jz      short loc_14000BA88
0x14000ba85  mov     [r9], r8d
0x14000ba88  mov     ebp, r8d
0x14000ba8b  mov     r15d, r8d
0x14000ba8e  mov     rsi, rdi
0x14000ba91  mov     rbx, [rcx+18h]
0x14000ba95  cmp     rbx, [r13+8]
0x14000ba99  jz      loc_14000BB26
0x14000ba9f  cmp     ebp, r12d
0x14000baa2  jnb     short loc_14000BB21
0x14000baa4  lea     rdx, [rbx+20h]
0x14000baa8  mov     rcx, rsi
0x14000baab  call    ?copy@CopyFromPairWstringToLpolestr@Windows@@SAJPEAPEAGPEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@Z; Windows::CopyFromPairWstringToLpolestr::copy(ushort * *,std::pair<std::wstring const,std::wstring> const *)
0x14000bab0  xor     r8d, r8d
0x14000bab3  mov     r15d, eax
0x14000bab6  test    eax, eax
0x14000bab8  js      short loc_14000BB1A
0x14000baba  add     rsi, 8
0x14000babe  cmp     [rbx+19h], r8b
0x14000bac2  jnz     short loc_14000BB09
0x14000bac4  mov     rcx, [rbx+10h]
0x14000bac8  cmp     [rcx+19h], r8b
0x14000bacc  jnz     short loc_14000BAED
0x14000bace  mov     rdx, [rcx]
0x14000bad1  cmp     [rdx+19h], r8b
0x14000bad5  jnz     short loc_14000BAE8
0x14000bad7  mov     rax, [rdx]
0x14000bada  mov     rbx, rdx
0x14000badd  mov     rdx, rax
0x14000bae0  cmp     [rax+19h], r8b
0x14000bae4  jz      short loc_14000BAD7
0x14000bae6  jmp     short loc_14000BB09
0x14000bae8  mov     rbx, rcx
0x14000baeb  jmp     short loc_14000BB09
0x14000baed  mov     rax, [rbx+8]
0x14000baf1  jmp     short loc_14000BB00
0x14000baf3  cmp     rbx, [rax+10h]
0x14000baf7  jnz     short loc_14000BB06
0x14000baf9  mov     rbx, rax
0x14000bafc  mov     rax, [rax+8]
0x14000bb00  cmp     [rax+19h], r8b
0x14000bb04  jz      short loc_14000BAF3
0x14000bb06  mov     rbx, rax
0x14000bb09  inc     ebp
0x14000bb0b  jmp     short loc_14000BA95
0x14000bb0d  mov     rcx, [rdi]; pv
0x14000bb10  add     rdi, 8
0x14000bb14  call    cs:__imp_CoTaskMemFree
0x14000bb1a  cmp     rdi, rsi
0x14000bb1d  jb      short loc_14000BB0D
0x14000bb1f  jmp     short loc_14000BB3C
0x14000bb21  test    r15d, r15d
0x14000bb24  js      short loc_14000BB3C
0x14000bb26  test    r14, r14
0x14000bb29  jz      short loc_14000BB2E
0x14000bb2b  mov     [r14], ebp
0x14000bb2e  cmp     ebp, r12d
0x14000bb31  jnb     short loc_14000BB3C
0x14000bb33  mov     [rsi], r8
0x14000bb36  mov     r15d, 1
0x14000bb3c  mov     [r13+18h], rbx
0x14000bb40  mov     eax, r15d
0x14000bb43  add     rsp, 28h
0x14000bb47  pop     r15
0x14000bb49  pop     r14
0x14000bb4b  pop     r13
0x14000bb4d  pop     r12
0x14000bb4f  pop     rdi
0x14000bb50  pop     rsi
0x14000bb51  pop     rbp
0x14000bb52  pop     rbx
0x14000bb53  retn
```
