# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000766c`
- end: `0x180007846`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `474`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180008c84`

## callees

- `0x180004518`
- `0x180004648`
- `0x180004684`
- `0x1800050fc`
- `0x1800074dc`
- `0x18000766c`
- `0x18000fc30`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800077f6`
- `KERNEL32!FreeLibrary` at `0x1800077f6`
- `KERNEL32!LoadLibraryExW` at `0x1800076b3`
- `KERNEL32!LoadLibraryExW` at `0x1800076b3`
- `KERNEL32!MultiByteToWideChar` at `0x1800077c1`
- `KERNEL32!MultiByteToWideChar` at `0x1800077c1`
- `KERNEL32!SizeofResource` at `0x180007716`
- `KERNEL32!SizeofResource` at `0x180007716`
- `KERNEL32!LoadResource` at `0x1800076fd`
- `KERNEL32!LoadResource` at `0x1800076fd`
- `KERNEL32!FindResourceExW` at `0x1800076df`
- `KERNEL32!FindResourceExW` at `0x1800076df`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v7; // rdi
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v10; // rsi
  unsigned int v11; // eax
  const CHAR *v12; // r14
  DWORD cchWideChar; // esi
  DWORD v14; // eax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  HMODULE v18; // [rsp+38h] [rbp-460h]
  _QWORD v19[3]; // [rsp+48h] [rbp-450h] BYREF
  LPWSTR v20; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v21[1032]; // [rsp+68h] [rbp-430h] BYREF

  v19[2] = 0;
  v19[1] = this;
  v19[0] = 0;
  v20 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v7 = Library;
  v18 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v20 != (LPWSTR)v21 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
    return Error;
  }
  Resource = FindResourceExW(Library, a4, (LPCWSTR)0x70, 0);
  v10 = Resource;
  if ( !Resource )
    goto LABEL_4;
  v12 = (const CHAR *)LoadResource(v7, Resource);
  if ( !v12 )
    goto LABEL_4;
  cchWideChar = SizeofResource(v7, v10);
  v14 = cchWideChar + 1;
  if ( cchWideChar + 1 >= cchWideChar )
  {
    try
    {
      if ( cchWideChar == -1 )
        goto LABEL_14;
      if ( 0xFFFFFFFFFFFFFFFFuLL / v14 < 2 )
        ATL::AtlThrowImpl(-2147024809);
      if ( 2 * (unsigned __int64)v14 <= 0x400 )
      {
LABEL_14:
        lpWideCharStr = (WCHAR *)v21;
        v20 = (LPWSTR)v21;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v20, 2LL * v14);
        lpWideCharStr = v20;
      }
    }
    catch ( ... )
    {
      v7 = v18;
      lpWideCharStr = v20;
    }
    if ( !lpWideCharStr )
    {
      Error = -2147024882;
LABEL_20:
      FreeLibrary(v7);
      goto LABEL_21;
    }
    v17 = MultiByteToWideChar(3u, 0, v12, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v17 )
    {
      v20[v17] = 0;
      v11 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v19, v20, a5);
      goto LABEL_19;
    }
LABEL_4:
    v11 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v11;
    goto LABEL_20;
  }
  if ( v20 != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000766c  mov     [rsp+arg_0], rbx
0x180007671  push    rsi
0x180007672  push    rdi
0x180007673  push    r14
0x180007675  sub     rsp, 480h
0x18000767c  mov     rax, cs:__security_cookie
0x180007683  xor     rax, rsp
0x180007686  mov     [rsp+498h+var_28], rax
0x18000768e  mov     rsi, r9
0x180007691  mov     rax, rdx
0x180007694  xor     ebx, ebx
0x180007696  mov     [rsp+498h+var_440], rbx
0x18000769b  mov     [rsp+498h+var_448], rcx
0x1800076a0  mov     [rsp+498h+var_450], rbx
0x1800076a5  mov     [rsp+498h+var_438], rbx
0x1800076aa  xor     edx, edx; hFile
0x1800076ac  lea     r8d, [rbx+2]; dwFlags
0x1800076b0  mov     rcx, rax; lpLibFileName
0x1800076b3  call    cs:__imp_LoadLibraryExW
0x1800076b9  mov     rdi, rax
0x1800076bc  mov     [rsp+498h+var_460], rax
0x1800076c1  test    rax, rax
0x1800076c4  jnz     short loc_1800076D2
0x1800076c6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800076cb  mov     ebx, eax
0x1800076cd  jmp     loc_1800077FD
0x1800076d2  xor     r9d, r9d; wLanguage
0x1800076d5  lea     r8d, [r9+70h]; lpName
0x1800076d9  mov     rdx, rsi; lpType
0x1800076dc  mov     rcx, rdi; hModule
0x1800076df  call    cs:__imp_FindResourceExW
0x1800076e5  mov     rsi, rax
0x1800076e8  test    rax, rax
0x1800076eb  jnz     short loc_1800076F7
0x1800076ed  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800076f2  jmp     loc_1800077F1
0x1800076f7  mov     rdx, rsi; hResInfo
0x1800076fa  mov     rcx, rdi; hModule
0x1800076fd  call    cs:__imp_LoadResource
0x180007703  mov     r14, rax
0x180007706  mov     [rsp+498h+var_458], rax
0x18000770b  test    rax, rax
0x18000770e  jz      short loc_1800076ED
0x180007710  mov     rdx, rsi; hResInfo
0x180007713  mov     rcx, rdi; hModule
0x180007716  call    cs:__imp_SizeofResource
0x18000771c  mov     esi, eax
0x18000771e  mov     [rsp+498h+var_468], eax
0x180007722  inc     eax
0x180007724  cmp     eax, esi
0x180007726  jnb     short loc_180007749
0x180007728  lea     rax, [rsp+498h+var_430]
0x18000772d  cmp     [rsp+498h+var_438], rax
0x180007732  jz      short loc_18000773F
0x180007734  lea     rcx, [rsp+498h+var_438]
0x180007739  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000773e  nop
0x18000773f  mov     eax, 8007000Eh
0x180007744  jmp     loc_180007816
0x180007749  test    eax, eax
0x18000774b  jz      short loc_180007780
0x18000774d  mov     ecx, eax
0x18000774f  xor     edx, edx
0x180007751  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007755  div     rcx
0x180007758  cmp     rax, 2
0x18000775c  jb      loc_18000783A
0x180007762  lea     rdx, [rcx+rcx]
0x180007766  cmp     rdx, 400h
0x18000776d  jbe     short loc_180007780
0x18000776f  lea     rcx, [rsp+498h+var_438]
0x180007774  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180007779  mov     rax, [rsp+498h+var_438]
0x18000777e  jmp     short loc_18000778A
0x180007780  lea     rax, [rsp+498h+var_430]
0x180007785  mov     [rsp+498h+var_438], rax
0x18000778a  jmp     short loc_1800077A1
0x18000778c  xor     ebx, ebx
0x18000778e  mov     rdi, [rsp+498h+var_460]
0x180007793  mov     r14, [rsp+498h+var_458]
0x180007798  mov     esi, [rsp+498h+var_468]
0x18000779c  mov     rax, [rsp+498h+var_438]
0x1800077a1  test    rax, rax
0x1800077a4  jnz     short loc_1800077AD
0x1800077a6  mov     ebx, 8007000Eh
0x1800077ab  jmp     short loc_1800077F3
0x1800077ad  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x1800077b1  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x1800077b6  mov     r9d, esi; cbMultiByte
0x1800077b9  mov     r8, r14; lpMultiByteStr
0x1800077bc  xor     edx, edx; dwFlags
0x1800077be  lea     ecx, [rdx+3]; CodePage
0x1800077c1  call    cs:__imp_MultiByteToWideChar
0x1800077c7  test    eax, eax
0x1800077c9  jz      loc_1800076ED
0x1800077cf  mov     ecx, eax
0x1800077d1  mov     rax, [rsp+498h+var_438]
0x1800077d6  mov     [rax+rcx*2], bx
0x1800077da  mov     r8d, [rsp+498h+arg_20]; int
0x1800077e2  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x1800077e7  lea     rcx, [rsp+498h+var_450]; this
0x1800077ec  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800077f1  mov     ebx, eax
0x1800077f3  mov     rcx, rdi; hLibModule
0x1800077f6  call    cs:__imp_FreeLibrary
0x1800077fc  nop
0x1800077fd  lea     rax, [rsp+498h+var_430]
0x180007802  cmp     [rsp+498h+var_438], rax
0x180007807  jz      short loc_180007814
0x180007809  lea     rcx, [rsp+498h+var_438]
0x18000780e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180007813  nop
0x180007814  mov     eax, ebx
0x180007816  mov     rcx, [rsp+498h+var_28]
0x18000781e  xor     rcx, rsp; StackCookie
0x180007821  call    __security_check_cookie
0x180007826  mov     rbx, [rsp+498h+arg_0]
0x18000782e  add     rsp, 480h
0x180007835  pop     r14
0x180007837  pop     rdi
0x180007838  pop     rsi
0x180007839  retn
0x18000783a  mov     ecx, 80070057h; int
0x18000783f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
