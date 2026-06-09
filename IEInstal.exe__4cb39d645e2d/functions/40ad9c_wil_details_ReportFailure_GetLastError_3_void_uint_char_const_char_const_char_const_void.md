# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x40ad9c`
- end: `0x40adf3`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YGKPAXIPBD110@Z`
- size: `87`
- prototype: `void __thiscall __noreturn(void *this, int, int, int, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x40ae34`

## callees

- `0x40a692`
- `0x40a986`
- `0x40ad3d`

## string_xrefs

- `0x40adb0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __thiscall __noreturn wil::details::ReportFailure_GetLastError<3>(void *this, int a2, int a3, int a4, char *a5)
{
  int LastErrorFail; // eax
  unsigned int v6; // ecx
  int *v7; // eax
  const char *v8; // [esp+0h] [ebp-30h]
  const char *v9; // [esp+4h] [ebp-2Ch]
  void *v10; // [esp+8h] [ebp-28h]
  _BYTE v11[16]; // [esp+10h] [ebp-20h] BYREF
  int v12; // [esp+20h] [ebp-10h]
  int v13; // [esp+24h] [ebp-Ch]
  int v14; // [esp+28h] [ebp-8h]
  void *v15; // [esp+2Ch] [ebp-4h]

  v15 = this;
  LastErrorFail = wil::details::GetLastErrorFail(
                    (wil::details *)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    this,
                    (unsigned int)this,
                    a5,
                    v8,
                    v9,
                    v10);
  v6 = (unsigned __int16)LastErrorFail | 0x80070000;
  if ( LastErrorFail <= 0 )
    v6 = LastErrorFail;
  v7 = (int *)wil::details::ResultStatus::FromResult(v6, v11);
  v12 = *v7;
  v13 = v7[1];
  v14 = v7[2];
  wil::details::ReportFailure_Base<3,0>();
}

```

## disassembly

```asm
0x40ad9c  mov     edi, edi
0x40ad9e  push    ebp
0x40ad9f  mov     ebp, esp
0x40ada1  sub     esp, 24h
0x40ada4  push    ebx; void *
0x40ada5  push    esi; char *
0x40ada6  push    edi; char *
0x40ada7  push    [ebp+arg_C]; char *
0x40adaa  mov     eax, ecx
0x40adac  mov     ebx, edx
0x40adae  push    ecx; unsigned int
0x40adaf  push    ecx; void *
0x40adb0  push    offset aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x40adb5  mov     [ebp+var_4], eax
0x40adb8  call    ?GetLastErrorFail@details@wil@@YGKPAXIPBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x40adbd  movzx   ecx, ax
0x40adc0  or      ecx, 80070000h
0x40adc6  test    eax, eax
0x40adc8  cmovle  ecx, eax
0x40adcb  lea     eax, [ebp+var_20]
0x40adce  push    eax
0x40adcf  call    ?FromResult@ResultStatus@details@wil@@SG?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x40add4  mov     ecx, [ebp+var_4]
0x40add7  lea     edi, [ebp+var_10]
0x40adda  mov     esi, eax
0x40addc  sub     esp, 0Ch
0x40addf  lea     eax, [ebp+var_10]
0x40ade2  mov     edx, ebx
0x40ade4  movsd
0x40ade5  push    eax
0x40ade6  push    [ebp+arg_C]
0x40ade9  movsd
0x40adea  sub     esp, 0Ch
0x40aded  movsd
0x40adee  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YGXPAXIPBD110ABUResultStatus@01@PBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
