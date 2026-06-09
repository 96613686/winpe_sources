# std::deque<std::unique_ptr<ipx::mtf::CClientDataSource,std::default_delete<ipx::mtf::CClientDataSource>>,std::allocator<std::unique_ptr<ipx::mtf::CClientDataSource,std::default_delete<ipx::mtf::CClientDataSource>>>>::operator[](unsigned __int64)

- ea: `0x180014848`
- end: `0x1800148e9`
- name: `??A?$deque@V?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@std@@V?$allocator@V?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@1@_K@Z`
- size: `161`
- prototype: ``
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x180014a00`
- `0x180014c90`
- `0x1800150a0`
- `0x180015960`
- `0x180015ce0`
- `0x180015e80`
- `0x180016280`
- `0x1800163a0`
- `0x180016430`
- `0x180016750`
- `0x1800189d0`
- `0x180019b00`
- `0x18001cdd4`
- `0x18001cf68`

## callees

- `0x180002de0`
- `0x180002e68`
- `0x180014848`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::deque<std::unique_ptr<ipx::mtf::CClientDataSource>>::operator[](__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 *****v4; // r8
  __int64 ***v5; // rax
  unsigned __int64 v6; // rbx
  __int64 **v7; // rax
  __int64 v8; // rdx
  __int64 *v10; // rax
  char v11; // [rsp+30h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 24);
  v4 = *(__int64 ******)a1;
  v5 = 0;
  if ( *(_QWORD *)a1 )
  {
    if ( *v4 )
    {
      v5 = **v4;
    }
    else
    {
      std::_Lockit::_Lockit((std::_Lockit *)&v11, 3);
      std::_Lockit::~_Lockit((std::_Lockit *)&v11);
      v5 = 0;
    }
  }
  v6 = v3 + a2;
  if ( v5 )
  {
    v7 = *v5;
    if ( v7 )
    {
      v10 = *v7;
      if ( v10 )
      {
        v8 = *v10;
        return *(_QWORD *)(*(_QWORD *)(v8 + 8) + 8 * ((*(_QWORD *)(v8 + 16) - 1LL) & (v6 >> 1))) + 8 * (v6 & 1);
      }
    }
    else
    {
      std::_Lockit::_Lockit((std::_Lockit *)&v11, 3);
      std::_Lockit::~_Lockit((std::_Lockit *)&v11);
    }
  }
  v8 = 0;
  return *(_QWORD *)(*(_QWORD *)(v8 + 8) + 8 * ((*(_QWORD *)(v8 + 16) - 1LL) & (v6 >> 1))) + 8 * (v6 & 1);
}

```

## disassembly

```asm
0x180014848  mov     [rsp+arg_8], rbx
0x18001484d  push    rdi
0x18001484e  sub     rsp, 20h
0x180014852  mov     rbx, rdx
0x180014855  mov     rdi, [rcx+18h]
0x180014859  mov     r8, [rcx]
0x18001485c  xor     eax, eax
0x18001485e  test    r8, r8
0x180014861  jz      short loc_180014889
0x180014863  mov     rax, [r8]
0x180014866  test    rax, rax
0x180014869  jnz     short loc_180014886
0x18001486b  lea     edx, [rax+3]; int
0x18001486e  lea     rcx, [rsp+28h+arg_0]; this
0x180014873  call    ??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x180014878  lea     rcx, [rsp+28h+arg_0]; this
0x18001487d  call    ??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x180014882  xor     eax, eax
0x180014884  jmp     short loc_180014889
0x180014886  mov     rax, [rax]
0x180014889  add     rbx, rdi
0x18001488c  test    rax, rax
0x18001488f  jz      short loc_1800148B0
0x180014891  mov     rax, [rax]
0x180014894  test    rax, rax
0x180014897  jnz     short loc_1800148DC
0x180014899  lea     edx, [rax+3]; int
0x18001489c  lea     rcx, [rsp+28h+arg_0]; this
0x1800148a1  call    ??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x1800148a6  lea     rcx, [rsp+28h+arg_0]; this
0x1800148ab  call    ??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x1800148b0  xor     edx, edx
0x1800148b2  mov     rcx, rbx
0x1800148b5  shr     rcx, 1
0x1800148b8  mov     rax, [rdx+10h]
0x1800148bc  dec     rax
0x1800148bf  and     rcx, rax
0x1800148c2  mov     rax, [rdx+8]
0x1800148c6  and     ebx, 1
0x1800148c9  mov     rax, [rax+rcx*8]
0x1800148cd  lea     rax, [rax+rbx*8]
0x1800148d1  mov     rbx, [rsp+28h+arg_8]
0x1800148d6  add     rsp, 20h
0x1800148da  pop     rdi
0x1800148db  retn
0x1800148dc  mov     rax, [rax]
0x1800148df  test    rax, rax
0x1800148e2  jz      short loc_1800148B0
0x1800148e4  mov     rdx, [rax]
0x1800148e7  jmp     short loc_1800148B2
```
