# System.Windows.Documents.RtfControls::.cctor

- ea: `0xe74c0`
- end: `0xeda2d`
- name: `System.Windows.Documents.RtfControls::.cctor`
- size: `25965`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0xe7490`
- `0xe74a0`
- `0xe74b0`
- `0xedee0`

## string_xrefs

- `0xe753b`: `acccomma`
- `0xe775f`: `aftnnzodiacl`
- `0xe8906`: `comment`
- `0xe891c`: `company`
- `0xe8b14`: `deleted`
- `0xe8d2d`: `doccomm`
- `0xe8d43`: `doctemp`
- `0xe8f45`: `dpcominusx`
- `0xe8f56`: `dpcominusy`
- `0xe9e17`: `ftnnzodiacl`
- `0xea084`: `hlinkbase`
- `0xea288`: `jcompress`
- `0xea5b2`: `leveltemplateid`
- `0xea6e1`: `linkself`
- `0xea6f7`: `linkstyles`
- `0xea708`: `linkval`
- `0xea8ee`: `listtemplateid`
- `0xeae8b`: `objautlink`
- `0xeaf93`: `objlink`
- `0xeb09b`: `objupdate`
- `0xeb5ae`: `pgnzodiacl`
- `0xebf17`: `pnzodiacl`
- `0xec66e`: `scompose`
- `0xecd48`: `template`

## pseudocode

```c

```

## disassembly

```asm
0xe74c0  ldc.i4   0x492
0xe74c5  newarr   System.Windows.Documents.RtfControlWordInfo
0xe74ca  dup
0xe74cb  ldc.i4.0
0xe74cc  ldc.i4.0
0xe74cd  ldstr    aAb// "ab"
0xe74d2  ldc.i4   0x81
0xe74d7  newobj   instance void System.Windows.Documents.RtfControlWordInfo::.ctor(valuetype System.Windows.Documents.RtfControlWord controlWord, string controlName, unsigned int32 flags)
0xe74dc  stelem.ref
0xe74dd  dup
0xe74de  ldc.i4.1
0xe74df  ldc.i4.1
0xe74e0  ldstr    aAbsh// "absh"
0xe74e5  ldc.i4   0x400004
0xe74ea  newobj   instance void System.Windows.Documents.RtfControlWordInfo::.ctor(valuetype System.Windows.Documents.RtfControlWord controlWord, string controlName, unsigned int32 flags)
0xe74ef  stelem.ref
0xe74f0  dup
0xe74f1  ldc.i4.2
0xe74f2  ldc.i4.2
0xe74f3  ldstr    aAbslock// "abslock"
0xe74f8  ldc.i4   0x400002
0xe74fd  newobj   instance void System.Windows.Documents.RtfControlWordInfo::.ctor(valuetype System.Windows.Documents.RtfControlWord controlWord, string controlName, unsigned int32 flags)
0xe7502  stelem.ref
0xe7503  dup
0xe7504  ldc.i4.3
0xe7505  ldstr    aAbsnoovrlp// "absnoovrlp"
0xe750a  ldc.i4   0x400021
0xe750f  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe7514  stelem.ref
0xe7515  dup
0xe7516  ldc.i4.4
0xe7517  ldstr    aAbsw// "absw"
0xe751c  ldc.i4   0x400004
0xe7521  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe7526  stelem.ref
0xe7527  dup
0xe7528  ldc.i4.5
0xe7529  ldstr    aAcaps// "acaps"
0xe752e  ldc.i4   0x81
0xe7533  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe7538  stelem.ref
0xe7539  dup
0xe753a  ldc.i4.6
0xe753b  ldstr    aAcccomma// "acccomma"
0xe7540  ldc.i4   0x101
0xe7545  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe754a  stelem.ref
0xe754b  dup
0xe754c  ldc.i4.7
0xe754d  ldstr    aAccdot// "accdot"
0xe7552  ldc.i4   0x101
0xe7557  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe755c  stelem.ref
0xe755d  dup
0xe755e  ldc.i4.8
0xe755f  ldstr    aAccnone// "accnone"
0xe7564  ldc.i4   0x101
0xe7569  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe756e  stelem.ref
0xe756f  dup
0xe7570  ldc.i4.s 9
0xe7572  ldstr    aAcf// "acf"
0xe7577  ldc.i4   0x84
0xe757c  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe7581  stelem.ref
0xe7582  dup
0xe7583  ldc.i4.s 0xA
0xe7585  ldstr    aAdditive// "additive"
0xe758a  ldc.i4   0x10002
0xe758f  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe7594  stelem.ref
0xe7595  dup
0xe7596  ldc.i4.s 0xB
0xe7598  ldstr    aAdjustright// "adjustright"
0xe759d  ldc.i4   0x1002
0xe75a2  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe75a7  stelem.ref
0xe75a8  dup
0xe75a9  ldc.i4.s 0xC
0xe75ab  ldstr    aAdn// "adn"
0xe75b0  ldc.i4   0x84
0xe75b5  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe75ba  stelem.ref
0xe75bb  dup
0xe75bc  ldc.i4.s 0xD
0xe75be  ldstr    aAenddoc// "aenddoc"
0xe75c3  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe75c8  stelem.ref
0xe75c9  dup
0xe75ca  ldc.i4.s 0xE
0xe75cc  ldstr    aAendnotes// "aendnotes"
0xe75d1  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe75d6  stelem.ref
0xe75d7  dup
0xe75d8  ldc.i4.s 0xF
0xe75da  ldstr    aAexpnd// "aexpnd"
0xe75df  ldc.i4   0x84
0xe75e4  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe75e9  stelem.ref
0xe75ea  dup
0xe75eb  ldc.i4.s 0x10
0xe75ed  ldstr    aAf// "af"
0xe75f2  ldc.i4   0x84
0xe75f7  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe75fc  stelem.ref
0xe75fd  dup
0xe75fe  ldc.i4.s 0x11
0xe7600  ldstr    aAffixed// "affixed"
0xe7605  ldc.i4   0x202
0xe760a  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe760f  stelem.ref
0xe7610  dup
0xe7611  ldc.i4.s 0x12
0xe7613  ldstr    aAfs// "afs"
0xe7618  ldc.i4   0x84
0xe761d  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe7622  stelem.ref
0xe7623  dup
0xe7624  ldc.i4.s 0x13
0xe7626  ldstr    aAftnbj// "aftnbj"
0xe762b  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe7630  stelem.ref
0xe7631  dup
0xe7632  ldc.i4.s 0x14
0xe7634  ldstr    aAftncn// "aftncn"
0xe7639  ldc.i4   0x2008
0xe763e  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe7643  stelem.ref
0xe7644  dup
0xe7645  ldc.i4.s 0x15
0xe7647  ldstr    aAftnnalc// "aftnnalc"
0xe764c  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe7651  stelem.ref
0xe7652  dup
0xe7653  ldc.i4.s 0x16
0xe7655  ldstr    aAftnnar// "aftnnar"
0xe765a  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe765f  stelem.ref
0xe7660  dup
0xe7661  ldc.i4.s 0x17
0xe7663  ldstr    aAftnnauc// "aftnnauc"
0xe7668  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe766d  stelem.ref
0xe766e  dup
0xe766f  ldc.i4.s 0x18
0xe7671  ldstr    aAftnnchi// "aftnnchi"
0xe7676  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe767b  stelem.ref
0xe767c  dup
0xe767d  ldc.i4.s 0x19
0xe767f  ldstr    aAftnnchosung// "aftnnchosung"
0xe7684  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe7689  stelem.ref
0xe768a  dup
0xe768b  ldc.i4.s 0x1A
0xe768d  ldstr    aAftnncnum// "aftnncnum"
0xe7692  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe7697  stelem.ref
0xe7698  dup
0xe7699  ldc.i4.s 0x1B
0xe769b  ldstr    aAftnndbar// "aftnndbar"
0xe76a0  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe76a5  stelem.ref
0xe76a6  dup
0xe76a7  ldc.i4.s 0x1C
0xe76a9  ldstr    aAftnndbnum// "aftnndbnum"
0xe76ae  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe76b3  stelem.ref
0xe76b4  dup
0xe76b5  ldc.i4.s 0x1D
0xe76b7  ldstr    aAftnndbnumd// "aftnndbnumd"
0xe76bc  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe76c1  stelem.ref
0xe76c2  dup
0xe76c3  ldc.i4.s 0x1E
0xe76c5  ldstr    aAftnndbnumk// "aftnndbnumk"
0xe76ca  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe76cf  stelem.ref
0xe76d0  dup
0xe76d1  ldc.i4.s 0x1F
0xe76d3  ldstr    aAftnndbnumt// "aftnndbnumt"
0xe76d8  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe76dd  stelem.ref
0xe76de  dup
0xe76df  ldc.i4.s 0x20
0xe76e1  ldstr    aAftnnganada// "aftnnganada"
0xe76e6  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe76eb  stelem.ref
0xe76ec  dup
0xe76ed  ldc.i4.s 0x21
0xe76ef  ldstr    aAftnngbnum// "aftnngbnum"
0xe76f4  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe76f9  stelem.ref
0xe76fa  dup
0xe76fb  ldc.i4.s 0x22
0xe76fd  ldstr    aAftnngbnumd// "aftnngbnumd"
0xe7702  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe7707  stelem.ref
0xe7708  dup
0xe7709  ldc.i4.s 0x23
0xe770b  ldstr    aAftnngbnumk// "aftnngbnumk"
0xe7710  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe7715  stelem.ref
0xe7716  dup
0xe7717  ldc.i4.s 0x24
0xe7719  ldstr    aAftnngbnuml// "aftnngbnuml"
0xe771e  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe7723  stelem.ref
0xe7724  dup
0xe7725  ldc.i4.s 0x25
0xe7727  ldstr    aAftnnrlc// "aftnnrlc"
0xe772c  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe7731  stelem.ref
0xe7732  dup
0xe7733  ldc.i4.s 0x26
0xe7735  ldstr    aAftnnruc// "aftnnruc"
0xe773a  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe773f  stelem.ref
0xe7740  dup
0xe7741  ldc.i4.s 0x27
0xe7743  ldstr    aAftnnzodiac// "aftnnzodiac"
0xe7748  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe774d  stelem.ref
0xe774e  dup
0xe774f  ldc.i4.s 0x28
0xe7751  ldstr    aAftnnzodiacd// "aftnnzodiacd"
0xe7756  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe775b  stelem.ref
0xe775c  dup
0xe775d  ldc.i4.s 0x29
0xe775f  ldstr    aAftnnzodiacl// "aftnnzodiacl"
0xe7764  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe7769  stelem.ref
0xe776a  dup
0xe776b  ldc.i4.s 0x2A
0xe776d  ldstr    aAftnrestart// "aftnrestart"
0xe7772  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe7777  stelem.ref
0xe7778  dup
0xe7779  ldc.i4.s 0x2B
0xe777b  ldstr    aAftnrstcont// "aftnrstcont"
0xe7780  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe7785  stelem.ref
0xe7786  dup
0xe7787  ldc.i4.s 0x2C
0xe7789  ldstr    aAftnsep// "aftnsep"
0xe778e  ldc.i4   0x2008
0xe7793  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe7798  stelem.ref
0xe7799  dup
0xe779a  ldc.i4.s 0x2D
0xe779c  ldstr    aAftnsepc// "aftnsepc"
0xe77a1  ldc.i4   0x2008
0xe77a6  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe77ab  stelem.ref
0xe77ac  dup
0xe77ad  ldc.i4.s 0x2E
0xe77af  ldstr    aAftnstart// "aftnstart"
0xe77b4  ldc.i4   0x2004
0xe77b9  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe77be  stelem.ref
0xe77bf  dup
0xe77c0  ldc.i4.s 0x2F
0xe77c2  ldstr    aAftntj// "aftntj"
0xe77c7  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe77cc  stelem.ref
0xe77cd  dup
0xe77ce  ldc.i4.s 0x30
0xe77d0  ldstr    aAi// "ai"
0xe77d5  ldc.i4   0x81
0xe77da  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe77df  stelem.ref
0xe77e0  dup
0xe77e1  ldc.i4.s 0x31
0xe77e3  ldstr    aAlang// "alang"
0xe77e8  ldc.i4   0x84
0xe77ed  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe77f2  stelem.ref
0xe77f3  dup
0xe77f4  ldc.i4.s 0x32
0xe77f6  ldstr    aAllprot// "allprot"
0xe77fb  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe7800  stelem.ref
0xe7801  dup
0xe7802  ldc.i4.s 0x33
0xe7804  ldstr    aAlntblind// "alntblind"
0xe7809  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonDocPropsControlWord(string controlName)
0xe780e  stelem.ref
0xe780f  dup
0xe7810  ldc.i4.s 0x34
0xe7812  ldstr    aAlt_0// "alt"
0xe7817  ldc.i4   0x10002
0xe781c  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe7821  stelem.ref
0xe7822  dup
0xe7823  ldc.i4.s 0x35
0xe7825  ldstr    aAnimtext// "animtext"
0xe782a  ldc.i4   0x124
0xe782f  call     class System.Windows.Documents.RtfControlWordInfo System.Windows.Documents.RtfControls::CreateCommonControlWord(string controlName, unsigned int32 flags)
0xe7834  stelem.ref
  ... truncated ...
```
