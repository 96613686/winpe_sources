# CommonUtil::UtilRegSetValueInternal(HKEY__ *,wchar_t const *,ulong,unsigned __int64,void const *)

- ea: `0x140012928`
- end: `0x1400129bc`
- name: `?UtilRegSetValueInternal@CommonUtil@@YAJPEAUHKEY__@@PEB_WK_KPEBX@Z`
- size: `148`
- prototype: `int(CommonUtil *__hidden this, HKEY, const wchar_t *, unsigned int, unsigned __int64, const void *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012840`
- `0x1400128e4`
- `0x1400129bc`
- `0x140012a0c`

## callees

- `0x140012928`
- `0x140085d94`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140012958`
- `ADVAPI32!RegSetValueExW` at `0x140012958`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegSetValueInternal(
        CommonUtil *this,
        const WCHAR *a2,
        const wchar_t *a3,
        __int64 cbData,
        BYTE *lpData)
{
  int v5; // edi
  __int64 result; // rax
  LSTATUS v7; // ebx

  v5 = (int)a2;
  if ( (unsigned int)cbData != cbData )
    return 2147942487LL;
  v7 = RegSetValueExW((HKEY)this, a2, 0, (DWORD)a3, lpData, cbData);
  if ( !v7 )
    return 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_Sd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      24,
      (unsigned int)WPP_6244c2291bff3591cc9dc7d07223cad0_Traceguids,
      v5,
      v7);
  result = (unsigned __int16)v7 | 0x80070000;
  if ( v7 <= 0 )
    result = (unsigned int)v7;
  if ( (int)result >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x140012928  mov     [rsp+arg_0], rbx
0x14001292d  push    rdi
0x14001292e  sub     rsp, 30h
0x140012932  mov     eax, r9d
0x140012935  mov     rdi, rdx
0x140012938  cmp     rax, r9
0x14001293b  jz      short loc_140012944
0x14001293d  mov     eax, 80070057h
0x140012942  jmp     short loc_1400129B1
0x140012944  mov     [rsp+38h+cbData], eax; cbData
0x140012948  mov     r9d, r8d; dwType
0x14001294b  mov     rax, [rsp+38h+arg_20]
0x140012950  xor     r8d, r8d; Reserved
0x140012953  mov     [rsp+38h+lpData], rax; lpData
0x140012958  call    cs:__imp_RegSetValueExW
0x14001295e  mov     ebx, eax
0x140012960  test    eax, eax
0x140012962  jz      short loc_1400129AF
0x140012964  mov     rcx, cs:WPP_GLOBAL_Control
0x14001296b  lea     rax, WPP_GLOBAL_Control
0x140012972  cmp     rcx, rax
0x140012975  jz      short loc_140012999
0x140012977  test    byte ptr [rcx+1Ch], 1
0x14001297b  jz      short loc_140012999
0x14001297d  mov     rcx, [rcx+10h]
0x140012981  lea     r8, WPP_6244c2291bff3591cc9dc7d07223cad0_Traceguids
0x140012988  mov     edx, 18h
0x14001298d  mov     dword ptr [rsp+38h+lpData], ebx
0x140012991  mov     r9, rdi
0x140012994  call    WPP_SF_Sd
0x140012999  movzx   eax, bx
0x14001299c  or      eax, 80070000h
0x1400129a1  test    ebx, ebx
0x1400129a3  cmovle  eax, ebx
0x1400129a6  mov     ecx, eax
0x1400129a8  shr     ecx, 1Fh
0x1400129ab  test    cl, cl
0x1400129ad  jnz     short loc_1400129B1
0x1400129af  xor     eax, eax
0x1400129b1  mov     rbx, [rsp+38h+arg_0]
0x1400129b6  add     rsp, 30h
0x1400129ba  pop     rdi
0x1400129bb  retn
```
