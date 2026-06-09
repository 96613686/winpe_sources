# uus::Utility::GetArchFolderFromMachine(uint)

- ea: `0x180009e98`
- end: `0x180009f52`
- name: `?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z`
- size: `186`
- prototype: `_QWORD *__fastcall(_QWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a060`

## callees

- `0x180002f94`
- `0x180007940`
- `0x180008d18`
- `0x180009e98`

## pseudocode

```c
_QWORD *__fastcall uus::Utility::GetArchFolderFromMachine(_QWORD *a1, int a2)
{
  int v3; // edx
  int v4; // edx
  const char *v5; // rdx
  const unsigned __int16 *v6; // rdx
  unsigned __int64 v7; // r8
  _BYTE pExceptionObject[32]; // [rsp+28h] [rbp-20h] BYREF

  v3 = a2 - 332;
  if ( v3 )
  {
    v4 = v3 - 116;
    if ( v4 )
    {
      v5 = (const char *)(unsigned int)(v4 - 33956);
      if ( (_DWORD)v5 )
      {
        if ( (_DWORD)v5 != 9216 )
        {
          std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, v5);
          throw (std::runtime_error *)pExceptionObject;
        }
        v6 = uus::Const::archArm64;
        v7 = -1;
        do
          ++v7;
        while ( uus::Const::archArm64[v7] );
      }
      else
      {
        v6 = uus::Const::archX64;
        v7 = -1;
        do
          ++v7;
        while ( uus::Const::archX64[v7] );
      }
    }
    else
    {
      v6 = uus::Const::archArm;
      v7 = -1;
      do
        ++v7;
      while ( uus::Const::archArm[v7] );
    }
  }
  else
  {
    v6 = uus::Const::archX86;
    v7 = -1;
    do
      ++v7;
    while ( uus::Const::archX86[v7] );
  }
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  std::wstring::_Construct<1,unsigned short const *>(a1, v6, v7);
  return a1;
}

```

## disassembly

```asm
0x180009e98  push    rbx
0x180009e9a  sub     rsp, 40h
0x180009e9e  xor     eax, eax
0x180009ea0  mov     rbx, rcx
0x180009ea3  sub     edx, 14Ch
0x180009ea9  jz      short loc_180009F05
0x180009eab  sub     edx, 74h ; 't'
0x180009eae  jz      short loc_180009EEE
0x180009eb0  sub     edx, 84A4h; char *
0x180009eb6  jz      short loc_180009ED7
0x180009eb8  cmp     edx, 2400h
0x180009ebe  jnz     short loc_180009F36
0x180009ec0  mov     rdx, cs:?archArm64@Const@uus@@2PEBGEB; ushort const * const uus::Const::archArm64
0x180009ec7  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009ecb  inc     r8
0x180009ece  cmp     [rdx+r8*2], ax
0x180009ed3  jnz     short loc_180009ECB
0x180009ed5  jmp     short loc_180009F1A
0x180009ed7  mov     rdx, cs:?archX64@Const@uus@@2PEBGEB; ushort const * const uus::Const::archX64
0x180009ede  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009ee2  inc     r8
0x180009ee5  cmp     [rdx+r8*2], ax
0x180009eea  jnz     short loc_180009EE2
0x180009eec  jmp     short loc_180009F1A
0x180009eee  mov     rdx, cs:?archArm@Const@uus@@2PEBGEB; ushort const * const uus::Const::archArm
0x180009ef5  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009ef9  inc     r8
0x180009efc  cmp     [rdx+r8*2], ax
0x180009f01  jnz     short loc_180009EF9
0x180009f03  jmp     short loc_180009F1A
0x180009f05  mov     rdx, cs:?archX86@Const@uus@@2PEBGEB; ushort const * const uus::Const::archX86
0x180009f0c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009f10  inc     r8
0x180009f13  cmp     [rdx+r8*2], ax
0x180009f18  jnz     short loc_180009F10
0x180009f1a  xorps   xmm0, xmm0
0x180009f1d  movups  xmmword ptr [rcx], xmm0
0x180009f20  mov     [rcx+10h], rax
0x180009f24  mov     [rcx+18h], rax
0x180009f28  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180009f2d  mov     rax, rbx
0x180009f30  add     rsp, 40h
0x180009f34  pop     rbx
0x180009f35  retn
0x180009f36  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180009f3b  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180009f40  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180009f47  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180009f4c  call    _CxxThrowException_0
```
